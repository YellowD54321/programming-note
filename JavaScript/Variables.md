## [Variable](https://javascript.info/variables#a-variable)

A [variable](https://en.wikipedia.org/wiki/Variable_(computer_science)) is a “named storage” for data. To create a variable in JavaScript, use the `let` keyword.

```js
let message = 'Hello';
```

In older scripts, you may also find another keyword: `var` instead of `let`:
```js
var message = 'Hello';
```

The `var` keyword is _almost_ the same as `let`. It also declares a variable, but in a slightly different, “old-school” way.

There are subtle differences between `let` and `var`, but they do not matter for us yet. We’ll cover them in detail in the chapter [The old "var"](https://javascript.info/var).

To declare a constant (unchanging) variable, use [[Constants|const]] instead of `let`.