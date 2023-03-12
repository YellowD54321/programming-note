# [Data types](https://javascript.info/types)

There are only two type of data in JavaScript: [[#^ba3009|primitive]] and [[object]].

We can put any type in a variable. For example, a variable can at one moment be a string and then store a number:
```js
// no error 
let message = "hello"; 
message = 123456;
```

See [[dynamically typed]]

## [primitive](https://javascript.info/types)

^ba3009

There are eight basic data types in JavaScript.

## [Number](https://javascript.info/types#number)

The _number_ type represents both integer and floating point numbers.

Besides regular numbers, there are so-called “special numeric values” which also belong to this data type: `Infinity`, `-Infinity` and `NaN`.
- `Infinity` represents the mathematical [Infinity](https://en.wikipedia.org/wiki/Infinity) ∞. It is a special value that’s greater than any number.
- `NaN` represents a computational error. It is a result of an incorrect or an undefined mathematical operation.

Read more about: [[Number]]

## [BigInt](https://javascript.info/types#bigint-type)

In JavaScript, the “number” type cannot represent integer values larger than `(2^53-1)` (that’s `9007199254740991`), or less than `-(2^53-1)` for negatives.

`BigInt` type was recently added to the language to represent integers of arbitrary length.
A `BigInt` value is created by appending `n` to the end of an integer:
```js
// the "n" at the end means it's a BigInt 
const bigInt = 1234567890123456789012345678901234567890n;
```

## [String](https://javascript.info/types#string)

A string in JavaScript must be surrounded by quotes.
In JavaScript, there are 3 types of quotes.

1.  Double quotes: `"Hello"`.
2.  Single quotes: `'Hello'`.
3.  Backticks: `` `Hello` ``.

Backticks are “extended functionality” quotes. They allow us to embed variables and expressions into a string by wrapping them in `${…}`,

## [Boolean (logical type)](https://javascript.info/types#boolean-logical-type)

The boolean type has only two values: `true` and `false`.

## [The “null” value](https://javascript.info/types#the-null-value)

The special `null` value does not belong to any of the types described above.
It’s just a special value which represents “nothing”, “empty” or “value unknown”.

## [The “undefined” value](https://javascript.info/types#the-undefined-value)

The special value `undefined` also stands apart. It makes a type of its own, just like `null`.
The meaning of `undefined` is “value is not assigned”.

## [Objects and Symbols](https://javascript.info/types#objects-and-symbols)

In contrast, [[object|objects]] are used to store collections of data and more complex entities.

The [[symbol]] type is used to create unique identifiers for objects.

## [The typeof operator](https://javascript.info/types#type-typeof)

The `typeof` operator returns the type of the argument.

## [A primitive as an object](https://javascript.info/primitives-methods#a-primitive-as-an-object)

```js
let str = "Hello";

alert( str.toUpperCase() ); // HELLO
```

1.  The string `str` is a primitive. So in the moment of accessing its property, a special object is created that knows the value of the string, and has useful methods, like `toUpperCase()`.
2.  That method runs and returns a new string (shown by `alert`).
3.  The special object is destroyed, leaving the primitive `str` alone.

So primitives can provide methods, but they still remain lightweight.