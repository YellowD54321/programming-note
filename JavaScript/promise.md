# promise
A promise in JavaScript is exactly what it sounds like - you use it to make a promise to do something, usually asynchronously. When the task completes, you either fulfill your promise or fail to do so. `Promise` is a constructor function, so you need to use the `new` keyword to create one. It takes a function, as its argument, with two parameters - `resolve` and `reject`. These are methods used to determine the outcome of the promise. The syntax looks like this:

```js
const myPromise = new Promise((resolve, reject) => {

});
```

A promise has three states: `pending`, `fulfilled`, and `rejected`. The promise you created in the last challenge is forever stuck in the `pending` state because you did not add a way to complete the promise. The `resolve` and `reject` parameters given to the promise argument are used to do this. `resolve` is used when you want your promise to succeed, and `reject` is used when you want it to fail. These are methods that take an argument, as seen below.

```js
const myPromise = new Promise((resolve, reject) => {
  if(condition here) {
    resolve("Promise was fulfilled");
  } else {
    reject("Promise was rejected");
  }
});
```