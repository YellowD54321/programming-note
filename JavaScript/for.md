# for

## [Continue to the next iteration](https://javascript.info/while-for#continue)
- No `break/continue` to the right side of ‘?’
```js
(i > 5) ? alert(i) : continue; // continue isn't allowed here
```

## [Labels for break/continue](https://javascript.info/while-for#labels-for-break-continue)

syntax:
```js
labelName: for (...) {
  ...
}
```

Use label can break/continue the outter loop.
```js
outer: for (let i = 0; i < 3; i++) {

  for (let j = 0; j < 3; j++) {

    let input = prompt(`Value at coords (${i},${j})`, '');

    // if an empty string or canceled, then break out of both loops
    if (!input) break outer; // (*)

    // do something with the value...
  }
}

alert('Done!');
```

