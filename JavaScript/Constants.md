## [Constants](https://javascript.info/variables#constants)

To declare a constant (unchanging) variable, use `const` instead of [[Variables|let]].
Constant cannot be reassigned. An attempt to do so would cause an error:
```js
const myBirthday = '18.04.1982';  
myBirthday = '01.01.2001'; // error, can't reassign the constant!
```

### [Uppercase constants](https://javascript.info/variables#uppercase-constants)

There is a widespread practice to use constants as aliases for difficult-to-remember values that are known prior to execution.

Such constants are named using capital letters and underscores.
```js
const COLOR_RED = "#F00";
const COLOR_GREEN = "#0F0";
const COLOR_BLUE = "#00F";
const COLOR_ORANGE = "#FF7F00";
// ...when we need to pick a color 
let color = COLOR_ORANGE;
alert(color);// #FF7F00
```

-   `COLOR_ORANGE` is much easier to remember than `"#FF7F00"`.
-   It is much easier to mistype `"#FF7F00"` than `COLOR_ORANGE`.
-   When reading the code, `COLOR_ORANGE` is much more meaningful than `#FF7F00`.

If a constant is not known prior to the page load, it’s named normally, not uppercase.