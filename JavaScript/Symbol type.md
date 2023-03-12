# [Symbol type](https://javascript.info/symbol)

By specification, only two primitive types may serve as object property keys:

-   string type, or
-   symbol type.

Otherwise, if one uses another type, such as number, it’s autoconverted to string. So that `obj[1]` is the same as `obj["1"]`, and `obj[true]` is the same as `obj["true"]`.

## [Symbols](https://javascript.info/symbol#symbols)

A “symbol” represents a unique identifier.

A value of this type can be created using `Symbol()`:

```js
let id1 = Symbol("id");
let id2 = Symbol("id");

alert(id1 == id2); // false
```

Symbols don’t auto-convert to a string:

```js
let id = Symbol("id");

alert(id); // TypeError: Cannot convert a Symbol value to a string  

alert(id.toString()); // Symbol(id), now it works

alert(id.description); // id
```

## [“Hidden” properties](https://javascript.info/symbol#hidden-properties)

Symbols allow us to create “hidden” properties of an object, that no other part of code can accidentally access or overwrite.

For example:

```js
let user = { // belongs to another code
  name: "John"
};

let id = Symbol("id");

user[id] = 1;

alert( user[id] ); // we can access the data using the symbol as the key
```

If we used a string `"id"` instead of a symbol:

```js
let user = { name: "John" };

// Our script uses "id" property
user.id = "Our id value";

// ...Another script also wants "id" for its purposes...

user.id = "Their id value"
// Boom! overwritten by another script!
```

### [Symbols in an object literal](https://javascript.info/symbol#symbols-in-an-object-literal)

If we want to use a symbol in an object literal `{...}`, we need square brackets around it.

```js
let id = Symbol("id");

let user = {
  name: "John",
  [id]: 123 // not "id": 123
};
```

### [Symbols are skipped by for…in](https://javascript.info/symbol#symbols-are-skipped-by-for-in)

Symbolic properties do not participate in `for..in` loop.

[Object.keys(user)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys) also ignores them.

[Object.assign](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/assign) copies both string and symbol properties:

```js
let id = Symbol("id");
let user = {
  [id]: 123
};

let clone = Object.assign({}, user);

alert( clone[id] ); // 123
```

## [Global symbols](https://javascript.info/symbol#global-symbols)

Usually all symbols are different, even if they have the same name.

We can create symbols in a _global symbol registry_ and access them later, and it guarantees that repeated accesses by the same name return exactly the same symbol.

In order to read (create if absent) a symbol from the registry, use `Symbol.for(key)`.

```js
// read from the global registry
let id = Symbol.for("id"); // if the symbol did not exist, it is created

// read it again (maybe from another part of the code)
let idAgain = Symbol.for("id");

// the same symbol
alert( id === idAgain ); // true
```

To do the opposite, use `Symbol.keyFor(sym)`:

```js
// get symbol by name
let sym = Symbol.for("name");
let sym2 = Symbol.for("id");

// get name by symbol
alert( Symbol.keyFor(sym) ); // name
alert( Symbol.keyFor(sym2) ); // id
```

## [System symbols](https://javascript.info/symbol#system-symbols)

There exist many “system” symbols that JavaScript uses internally, and we can use them to fine-tune various aspects of our objects.

They are listed in the specification in the [Well-known symbols](https://tc39.github.io/ecma262/#sec-well-known-symbols) table:

-   `Symbol.hasInstance`
-   `Symbol.isConcatSpreadable`
-   `Symbol.iterator`
-   `Symbol.toPrimitive`
-   …and so on.