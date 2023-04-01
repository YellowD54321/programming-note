# [setInterval()](https://developer.mozilla.org/en-US/docs/Web/API/setInterval)

The **`setInterval()`** method, offered on the [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window) and [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker) interfaces, repeatedly calls a function or executes a code snippet, with a fixed time delay between each call.

This method returns an interval ID which uniquely identifies the interval, so you can remove it later by calling [`clearInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/clearInterval "clearInterval()").

Because of  some scope reason, it might cause issues in some situation. For instance, this code won't work very well:

``` Javascript
const SomeComponent = () => {
	const [data, setData] = useState(1);

	useEffect(() => {
		const logInterval = setInterval(() => {
			console.log(data)
		}, 1000)
		return () => clearInterval(logInterval)
	}, [])

	// some other code

	return (
		<button onClick={() => setData(preValue => preValue + 1)}></button>
	)
}
```

We expect this code could print the current data value every second, however, it will always print the initial value, which is `1`, every second.

To solve this, we can create a new custom hook.

```Javascript
/**
* setInterval在第一個render時會將作用域固定，外部更動的變數無法影響到持續倒數的setInterval內部
* 造成只能讀取初始值的問題
* 使用custom hook來避免此問題，useRef會將callback function儲存，並可以在setInterval內使用變更的內容
*
* @param {Function} callback 時間到時執行的function
* @param {Integer} delay 倒數的時長(微秒)
* @returns setInterval本身回傳的內容，用於在外部也能夠clearInteger
*/
const useInterval = (callback, delay) => {
	const intervalRef = useRef();
	const callbackRef = useRef();

	useEffect(() => {
		callbackRef.current = callback;
	}, [callback]);

	useEffect(() => {
		intervalRef.current = setInterval(() => callbackRef.current(), delay);
		return () => {
			clearInterval(intervalRef.current);
			intervalRef.current = null;
		};
	}, [delay]);
	
	return intervalRef.current;
};

export default useInterval;
```