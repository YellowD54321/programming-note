# switch

## [Grouping of “case”](https://javascript.info/switch#grouping-of-case)

If there is no `break` then the execution continues with the next `case` without any checks.

So we can use this feature to group cases.

```js
let a = 3;

switch (a) {
  case 4:
    alert('Right!');
    break;

  case 3: // (*) grouped two cases
  case 5:
    alert('Wrong!');
    alert("Why don't you take a math class?");
    break;

  default:
    alert('The result is strange. Really.');
}
```

