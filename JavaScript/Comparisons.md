# [Comparisons](https://javascript.info/comparison)

-   Greater/less than: `a > b`, `a < b`.
-   Greater/less than or equals: `a >= b`, `a <= b`.
-   Equals: `a == b`, please note the double equality sign `==` means the equality test, while a single one `a = b` means an assignment.
-   Not equals: In maths the notation is `≠`, but in JavaScript it’s written as `a != b`.

All comparison operators return a boolean value: `true` or `false`.

## [String comparison](https://javascript.info/comparison#string-comparison)

To see whether a string is greater than another, JavaScript uses the so-called “dictionary” or “lexicographical” order.

In other words, strings are compared letter-by-letter.

```js
alert( 'Z' > 'A' ); // true 
alert( 'Glow' > 'Glee' ); // true
alert( 'Bee' > 'Be' ); // true
```

The algorithm to compare two strings is:

1.  Compare the first character of both strings.
2.  If the first character from the first string is greater (or less) than the other string’s, then the first string is greater (or less) than the second. We’re done.
3.  Otherwise, if both strings’ first characters are the same, compare the second characters the same way.
4.  Repeat until the end of either string.
5.  If both strings end at the same length, then they are equal. Otherwise, the longer string is greater.

## [Comparison of different types](https://javascript.info/comparison#comparison-of-different-types)

When comparing values of different types, JavaScript converts the values to numbers.

```js
alert( '2' > 1 ); // true, string '2' becomes a number 2 
alert( '01' == 1 ); // true, string '01' becomes a number 1
```

For boolean values, `true` becomes `1` and `false` becomes `0`.

```js
alert( true == 1 ); // true 
alert( false == 0 ); // true
```

## [Strict equality](https://javascript.info/comparison#strict-equality)

A strict equality operator `===` checks the equality without type conversion.

## [Comparison with null and undefined](https://javascript.info/comparison#comparison-with-null-and-undefined)

Equality check `==` and comparisons `> < >= <=` work differently.

```js
alert( null === undefined ); // false

alert( null == undefined ); // true
```

For maths and other comparisons `< > <= >=`
`null/undefined` are converted to numbers: `null` becomes `0`, while `undefined` becomes `NaN`.

```js
alert( null > 0 ); // (1) false 
alert( null == 0 ); // (2) false 
alert( null >= 0 ); // (3) true
```

The value `undefined` shouldn’t be compared to other values.

```js
alert( undefined > 0 ); // false (1) 
alert( undefined < 0 ); // false (2) 
alert( undefined == 0 ); // false (3)
```

-   Comparisons `(1)` and `(2)` return `false` because `undefined` gets converted to `NaN` and `NaN` is a special numeric value which returns `false` for all comparisons.
-   The equality check `(3)` returns `false` because `undefined` only equals `null`, `undefined`, and no other value.
