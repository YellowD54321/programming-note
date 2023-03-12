# this

It’s common that an object method needs to access the information stored in the object to do its job. To access the object, a method can use the `this` keyword.

## [“this” is not bound](https://javascript.info/object-methods#this-is-not-bound)

In JavaScript, keyword `this` behaves unlike most other programming languages. It can be used in any function, even if it’s not a method of an object.

The value of `this` is evaluated during the run-time, depending on the context.

If calling without an object,  `this == undefined`.

## [Arrow functions have no “this”](https://javascript.info/object-methods#arrow-functions-have-no-this)

Arrow functions are special: they don’t have their “own” `this`. If we reference `this` from such a function, it’s taken from the outer “normal” function.

