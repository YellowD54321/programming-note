# [Nullish coalescing operator '??'](https://javascript.info/nullish-coalescing-operator)

>#### NOTE
>This is a recent addition to the language. Old browsers may need [polyfills](https://javascript.info/polyfills).

The result of `a ?? b` is:

-   if `a` is defined, then `a`,
-   if `a` isn’t defined, then `b`.

In other words, `??` returns the first argument if it’s not `null/undefined`. Otherwise, the second one.

```js
result = a ?? b

//is the same as
result = (a !== null && a !== undefined) ? a : b;
```

The common use case for `??` is to provide a default value.

```js
let user;

alert(user ?? "Anonymous"); // Anonymous (user not defined)
```

## [Comparison with ||](https://javascript.info/nullish-coalescing-operator#comparison-with)

The [[Logical operators|OR]] `||` operator can be used in the same way as `??`.

The important difference between them is that:

-   `||` returns the first _truthy_ value.
-   `??` returns the first _defined_ value.

### [Using ?? with && or ||](https://javascript.info/nullish-coalescing-operator#using-with-or)

Due to safety reasons, JavaScript forbids using `??` together with `&&` and `||` operators, unless the precedence is explicitly specified with parentheses.

```js
let x = 1 && 2 ?? 3; // Syntax error
```

```js
let x = (1 && 2) ?? 3; // Works

alert(x); // 2
```

