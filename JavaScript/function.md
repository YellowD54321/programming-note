# function

## [Parameters](https://javascript.info/function-basics#parameters)

- A parameter is the variable listed inside the parentheses in the function declaration.
- An argument is the value that is passed to the function when it is called.

## [Function Expression vs Function Declaration](https://javascript.info/function-expressions#function-expression-vs-function-declaration)

```js
// Function Declaration
function sum(a, b) {
  return a + b;
}
```

```js
// Function Expression
let sum = function(a, b) {
  return a + b;
};
```

The difference is _when_ a function is created by the JavaScript engine.
- A Function Expression is created when the execution reaches it and is usable only from that moment.
- A Function Declaration can be called earlier than it is defined.
	- For example, a global Function Declaration is visible in the whole script, no matter where it is.
	That’s due to internal algorithms. When JavaScript prepares to run the script, it first looks for global Function Declarations in it and creates the functions. We can think of it as an “initialization stage”.

Read more about: [**Hoisting**](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting)

## [Arrow functions](https://javascript.info/arrow-functions-basics)

syntax:
```js
Alet func = (arg1, arg2, ..., argN) => expression;
```

[[this#Arrow functions have no “this” https javascript info object-methods arrow-functions-have-no-this | Arrow functions don't have `this`.]]

## [Constructor function](https://javascript.info/constructor-new#constructor-function)

Read more about: [[Constructor function]].