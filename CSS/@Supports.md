# @Supports
If some browser don't support css style, use @support instead.

ex:
```
.list-header {
	position: relative;
}

@support (position: sticky) {
	.list-header {
		position: sticky;
		top: 0;
	}
}
```
which means 'if this browser doesn't support sticky, go using position: relative'.