*When you see this sentence, you must be stucked by some loop asychronous issues.*

To finish the asynchronous with current sequence:
```Javascript
const results = await Promise.all(
	dataIds.map(async (id) => {
		return getApiData(id)
	})
)
```

or use `for` loop:

```Javascript
for (id of dataIds) {
	await getApiData(id)
}
```

More complicate issues, read these article:
- [Asynchronous array functions in Javascript](https://advancedweb.hu/asynchronous-array-functions-in-javascript/)
- [How to use async functions with Array.reduce in Javascript](https://advancedweb.hu/how-to-use-async-functions-with-array-reduce-in-javascript/)
- [How to use async functions with Array.map in Javascript](https://advancedweb.hu/how-to-use-async-functions-with-array-map-in-javascript/)
- [How to use async functions with Array.forEach in Javascript](https://advancedweb.hu/how-to-use-async-functions-with-array-foreach-in-javascript/)
- [How to use async functions with Array.filter in Javascript](https://advancedweb.hu/how-to-use-async-functions-with-array-filter-in-javascript/)
- [How to use async functions with Array.some and every in Javascript](https://advancedweb.hu/how-to-use-async-functions-with-array-some-and-every-in-javascript/)
