# [Number](https://javascript.info/number)

The _number_ type represents both integer and floating point numbers.

Besides regular numbers, there are so-called “special numeric values” which also belong to this data type: `Infinity`, `-Infinity` and `NaN`.
- `Infinity` represents the mathematical [Infinity](https://en.wikipedia.org/wiki/Infinity) ∞. It is a special value that’s greater than any number.
- `NaN` represents a computational error. It is a result of an incorrect or an undefined mathematical operation.

## [More ways to write a number](https://javascript.info/number#more-ways-to-write-a-number)

`e` multiplies the number by `1` with the given zeroes count.

```js
let billion = 1_000_000_000;

let billion = 1e9;  // 1 billion, literally: 1 and 9 zeroes

alert( 7.3e9 );  // 7.3 billions (same as 7300000000 or 7_300_000_000)
```

```js
let mсs = 0.000001;

let mcs = 1e-6; // five zeroes to the left from 1
```

## [toString(base)](https://javascript.info/number#tostring-base)

The `base` can vary from `2` to `36`. By default it’s `10`.

```js
let num = 255;

alert( num.toString(16) );  // ff
alert( num.toString(2) );   // 11111111
```


## [Rounding](https://javascript.info/number#rounding)

- `Math.floor`
Rounds down: `3.1` becomes `3`, and `-1.1` becomes `-2`.

- `Math.ceil`
Rounds up: `3.1` becomes `4`, and `-1.1` becomes `-1`.

- `Math.round`
Rounds to the nearest integer: `3.1` becomes `3`, `3.6` becomes `4`, the middle case: `3.5` rounds up to `4` too.

- `Math.trunc` (not supported by Internet Explorer)
Removes anything after the decimal point without rounding: `3.1` becomes `3`, `-1.1` becomes `-1`.

- [toFixed(n)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed)
Rounds the number to `n` digits after the point and returns a string representation of the result.
The result of `toFixed` is a string.

```js
let num = 12.34;
alert( num.toFixed(1) ); // "12.3"
```

