# Objects

## [Square brackets](https://javascript.info/object#square-brackets)

To address to special key or to use variable to the key, we can use square brackets.
```js
let user = {};

// set
user["likes birds"] = true;

//or more complex
let fruit = 'apple';
let bag = {
  [fruit + 'Computers']: 5 // bag.appleComputers = 5
};
```

## [Property existence test, “in” operator](https://javascript.info/object#property-existence-test-in-operator)

To check if a property exists in object:
```js
let user = {};

alert( user.noSuchProperty === undefined ); // true means "no such property"
```

To check if `key` is in object:
```js
"key" in object
```

## [The "for..in" loop](https://javascript.info/object#forin)

Syntax:
```js
for (let key in object) {
  // executes the body for each key among object properties
}
```

### [Ordered like an object](https://javascript.info/object#ordered-like-an-object)

- Integer properties are sorted.
- Non-integer are listed in the creation order.

## [References](https://javascript.info/object-copy)

- When an object variable is copied, the reference is copied.

## [Cloning and merging](https://javascript.info/object-copy#cloning-and-merging-object-assign)

- `Object.assign` replicates an object, or even merge several objects.

Syntax: 
```js
Object.assign(dest, [src1, src2, src3...])
```

-   The first argument `dest` is a target object.
-   Further arguments `src1, ..., srcN` (can be as many as needed) are source objects.
-   It copies the properties of all source objects `src1, ..., srcN` into the target `dest`. In other words, properties of all arguments starting from the second are copied into the first object.
-   The call returns `dest`.
- If the copied property name already exists, it gets overwritten.

## [Nested cloning](https://javascript.info/object-copy#nested-cloning)

Read more about: [Shalllow copy v.s. Deep copy ](https://askie.today/javascript-deep-copy-swallow-copy/)

Using `Object.assign` or spread syntax`{...}` is a good way to clone an object, But it only does shallow copy.

To easily do deep copy, use JSON:
```js
let newObject = JSON.parse(JSON.stringify(oldObject))
```

## [[Symbol type]]

A “symbol” represents a unique identifier.

```js
let id1 = Symbol("id");
let id2 = Symbol("id");

alert(id1 == id2); // false
```


# [[Type Conversions#Object to primitive conversion https javascript info object-toprimitive |Object to primitive conversion]]

