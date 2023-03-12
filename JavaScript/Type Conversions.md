# [Type Conversions](https://javascript.info/type-conversions)

Most of the time, operators and functions automatically convert the values given to them to the right type.

See [[dynamically typed]]

## [String Conversion](https://javascript.info/type-conversions#string-conversion)

We can also call the `String(value)` function to convert a value to a string:
```js
let value = true; 
alert(typeof value); // boolean 

value = String(value); // now value is a string "true" 
alert(typeof value); // string_
```

## [Numeric Conversion](https://javascript.info/type-conversions#numeric-conversion)

Numeric conversion happens in mathematical functions and expressions automatically.

```js
alert( "6" / "2" ); // 3, strings are converted to numbers
```

We can use the `Number(value)` function to explicitly convert a `value` to a number:
```js
let str = "123"; 
alert(typeof str); // string 

let num = Number(str); // becomes a number 123 
alert(typeof num); // number
```

If the string is not a valid number, the result of such a conversion is `NaN`.
```js
let age = Number("an arbitrary string instead of a number"); 
alert(age); // NaN, conversion failed
```

`null` becomes zero.
`undefined` becomes `NaN`.

## [Boolean Conversion](https://javascript.info/type-conversions#boolean-conversion)

Boolean conversion performed explicitly with a call to `Boolean(value)`.

The conversion rule:
-   Values that are intuitively “empty”, like `0`, an empty string, `null`, `undefined`, and `NaN`, become `false`.
-   Other values become `true`.

```js
alert( Boolean(1) ); // true 
alert( Boolean(0) ); // false 
alert( Boolean("hello") ); // true 
alert( Boolean("") ); // false
```

String with zero `"0"` is `true`.

# [Object to primitive conversion](https://javascript.info/object-toprimitive)

1.  There’s no conversion to boolean. All objects are `true` in a boolean context, as simple as that. There exist only numeric and string conversions.
2.  The numeric conversion happens when we subtract objects or apply mathematical functions. For instance, `Date` objects (to be covered in the chapter [Date and time](https://javascript.info/date)) can be subtracted, and the result of `date1 - date2` is the time difference between two dates.
3.  As for the string conversion – it usually happens when we output an object with `alert(obj)` and in similar contexts.

There are three variants of type conversion, that happen in various situations. They’re called “hints”, as described in the [specification](https://tc39.github.io/ecma262/#sec-toprimitive):

1. `string`

For an object-to-string conversion, when we’re doing an operation on an object that expects a string, like `alert`:

```js
// output
alert(obj);

// using object as a property key
anotherObj[obj] = 123;
```

2. `number`

For an object-to-number conversion, like when we’re doing maths:

```js
// explicit conversion
let num = Number(obj);

// maths (except binary plus)
let n = +obj; // unary plus
let delta = date1 - date2;

// less/greater comparison
let greater = user1 > user2;
```

3. `default`

Occurs in rare cases when the operator is “not sure” what type to expect.

For instance, binary plus `+` can work both with strings (concatenates them) and numbers (adds them). So if a binary plus gets an object as an argument, it uses the `"default"` hint to convert it.

Also, if an object is compared using `==` with a string, number or a symbol, it’s also unclear which conversion should be done, so the `"default"` hint is used.

```js
// binary plus uses the "default" hint
let total = obj1 + obj2;

// obj == number uses the "default" hint
if (user == 1) { ... };
```


**To do the conversion, JavaScript tries to find and call three object methods:

1.  Call `obj[Symbol.toPrimitive](hint)` – the method with the symbolic key `Symbol.toPrimitive` (system symbol), if such method exists,
2.  Otherwise if hint is `"string"`
    -   try calling `obj.toString()` or `obj.valueOf()`, whatever exists.
3.  Otherwise if hint is `"number"` or `"default"`
    -   try calling `obj.valueOf()` or `obj.toString()`, whatever exists.

## [Symbol.toPrimitive](https://javascript.info/object-toprimitive#symbol-toprimitive)

There’s a built-in symbol named `Symbol.toPrimitive` that should be used to name the conversion method, like this:

```js
obj[Symbol.toPrimitive] = function(hint) {
  // here goes the code to convert this object to a primitive
  // it must return a primitive value
  // hint = one of "string", "number", "default"
};
```

If the method `Symbol.toPrimitive` exists, it’s used for all hints, and no more methods are needed.

```js
let user = {
  name: "John",
  money: 1000,

  [Symbol.toPrimitive](hint) {
    alert(`hint: ${hint}`);
    return hint == "string" ? `{name: "${this.name}"}` : this.money;
  }
};

// conversions demo:
alert(user); // hint: string -> {name: "John"}
alert(+user); // hint: number -> 1000
alert(user + 500); // hint: default -> 1500
```

## [toString/valueOf](https://javascript.info/object-toprimitive#tostring-valueof)

If there’s no `Symbol.toPrimitive` then JavaScript tries to find methods `toString` and `valueOf`:

-   For the `"string"` hint: call `toString` method, and if it doesn’t exist, then `valueOf` (so `toString` has the priority for string conversions).
-   For other hints: `valueOf`, and if it doesn’t exist, then `toString` (so `valueOf` has the priority for maths).

By default, a plain object has following `toString` and `valueOf` methods:

-   The `toString` method returns a string `"[object Object]"`.
-   The `valueOf` method returns the object itself.

```js
let user = {name: "John"};

alert(user); // [object Object]
alert(user.valueOf() === user); // true
```

```js
let user = {
  name: "John",
  money: 1000,

  // for hint="string"
  toString() {
    return `{name: "${this.name}"}`;
  },

  // for hint="number" or "default"
  valueOf() {
    return this.money;
  }

};

alert(user); // toString -> {name: "John"}
alert(+user); // valueOf -> 1000
alert(user + 500); // valueOf -> 1500
```

