# rules of ReactDOM.reder()

you can only create one parement in ReactDOM.reder().
so instead of using this one:
```
ReactDOM.render(

	<h1 className="header">This is JSX</h1><p>This is a paragraph</p>,
	
	document.getElementById("root")
)
```

instead using this one:
```
ReactDOM.render(

	<div>
	
		<h1 className="header">This is JSX</h1>
		
		<p>This is a paragraph</p>
		
	</div>,
	
	document.getElementById("root")

)
```