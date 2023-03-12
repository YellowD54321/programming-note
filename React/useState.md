# useState

```
const [count, setCount] = React.useState(0)

function add() {
	setCount(count + 1)
}
```

equals to:

```
const [count, setCount] = React.useState(0)

function add() {
	setCount(function() {
		return count + 1
	})
	
}
```

equals to:

```
const [count, setCount] = React.useState(0)

function add() {
	setCount(function(oldValue) {
		return oldValue + 1
	})
	
}
```

equals to:

```
const [count, setCount] = React.useState(0)

function add() {
	setCount(oldValue => oldValue + 1)
	
}
```

```
/**

* Note: if you ever need the old value of state

* to help you determine the new value of state,

* you should pass a callback function to your

* state setter function instead of using

* state directly. This callback function will

* receive the old value of state as its parameter,

* which you can then use to determine your new

* value of state.

*/
```