## [Maths](https://javascript.info/operators#maths)

The following math [[operators|operations]] are supported:

-   Addition `+`,
-   Subtraction `-`,
-   Multiplication `*`,
-   Division `/`,
-   Remainder `%`,
-   Exponentiation `**`.

### [Remainder %](https://javascript.info/operators#remainder)

The result of `a % b` is the [remainder](https://en.wikipedia.org/wiki/Remainder) of the integer division of `a` by `b`.

```js
alert( 5 % 2 ); // 1, a remainder of 5 divided by 2 
alert( 8 % 3 ); // 2, a remainder of 8 divided by 3
```

### [Exponentiation **](https://javascript.info/operators#exponentiation)

The exponentiation operator `a ** b` raises `a` to the power of `b`.

```js
alert( 2 ** 2 ); // 2² = 4 
alert( 2 ** 3 ); // 2³ = 8 
alert( 2 ** 4 ); // 2⁴ = 16
```

## [String concatenation with binary +](https://javascript.info/operators#string-concatenation-with-binary)

If the binary `+` is applied to strings, it merges (concatenates) them:

```js
let s = "my" + "string"; 
alert(s); // mystring
```

 If any of the operands is a string, then the other one is converted to a string too.

 ```js
alert(2 + 2 + '1' ); // "41" and not "221"
 ```

 ```js
 alert('1' + 2 + 2); // "122" and not "14"
```

The binary `+` is the only operator that supports strings in such a way. Other arithmetic operators work only with numbers and always convert their operands to numbers.

```js
alert( 6 - '2' ); // 4, converts '2' to a number 
alert( '6' / '2' ); // 3, converts both operands to numbers
```

## [Numeric conversion, unary +](https://javascript.info/operators#numeric-conversion-unary)

If the operand is not a number, the unary plus converts it into a number.
It actually does the same thing as `Number(...)`, but is shorter.

```js
// No effect on numbers 
let x = 1; 
alert( +x ); // 1

// Converts non-numbers 
alert( +true ); // 1 
alert( +"" ); // 0
```

## [Operator precedence](https://javascript.info/operators#operator-precedence)

[precedence table](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)

### [Chaining assignments](https://javascript.info/operators#chaining-assignments)

```js
let a, b, c; 
a = b = c = 2 + 2;

alert( a ); // 4 
alert( b ); // 4 
alert( c ); // 4
```

## [Bitwise operators](https://javascript.info/operators#bitwise-operators)

Bitwise operators treat arguments as 32-bit integer numbers and work on the level of their binary representation.

The list of operators:

-   AND ( `&` )
-   OR ( `|` )
-   XOR ( `^` )
-   NOT ( `~` )
-   LEFT SHIFT ( `<<` )
-   RIGHT SHIFT ( `>>` )
-   ZERO-FILL RIGHT SHIFT ( `>>>` )

## [Comma](https://javascript.info/operators#comma)

The comma operator `,` is one of the rarest and most unusual operators. Sometimes, it’s used to write shorter code, so we need to know it in order to understand what’s going on.

```js
let a = (1 + 2, 3 + 4);
alert( a ); // 7 (the result of 3 + 4)
```

The first expression `1 + 2` is evaluated and its result is thrown away. Then, `3 + 4` is evaluated and returned as the result.