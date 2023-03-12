# [Optional chaining '?.'](https://javascript.info/optional-chaining)

The optional chaining `?.` is a safe way to access nested object properties, even if an intermediate property doesn’t exist.

The optional chaining `?.` stops the evaluation if the value before `?.` is `undefined` or `null` and returns `undefined`.

## [Other variants: ?.(), ?.[]](https://javascript.info/optional-chaining#other-variants)

- `?.()` is used to call a function that may not exist.
- `?.[]` is used to call an array that may not exist.


>[!Don’t overuse the optional chaining]
>
>We should use `?.` only where it’s ok that something doesn’t exist.
>
>For example, if according to our code logic `user` object must exist, but `address` is optional, then we should write `user.address?.street`, but not `user?.address?.street`.
>
>Then, if `user` happens to be undefined, we’ll see a programming error about it and fix it. Otherwise, if we overuse `?.`, coding errors can be silenced where not appropriate, and become more difficult to debug.



