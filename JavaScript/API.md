to get an API from url:
```
fetch("https://api.imgflip.com/get_memes")

	.then(res => res.json())

	.then(data => <handle the data here>)
```

if the API isn't neccessary to render everytime, use ``useEffect`` to control when it should be rerender.