## [Constructor function](https://javascript.info/constructor-new#constructor-function)

Constructor functions technically are regular functions. There are two conventions though:

1.  They are named with capital letter first.
2.  They should be executed only with `"new"` operator.

Read more about: [[new]].

When a function is executed with `new`, it does the following steps:

1.  A new empty object is created and assigned to `this`.
2.  The function body executes. Usually it modifies `this`, adds new properties to it.
3.  The value of `this` is returned.

For example, `new User(...)` does something like:

```js
function User(name) {
  // this = {};  (implicitly)

  // add properties to this
  this.name = name;
  this.isAdmin = false;

  // return this;  (implicitly)
}
```

## [Return from constructors](https://javascript.info/constructor-new#return-from-constructors)

Usually, constructors do not have a `return` statement. Their task is to write all necessary stuff into `this`, and it automatically becomes the result.

But if there is a `return` statement, then the rule is simple:

-   If `return` is called with an object, then the object is returned instead of `this`.
-   If `return` is called with a primitive, it’s ignored.

## [Methods in constructor](https://javascript.info/constructor-new#methods-in-constructor)

