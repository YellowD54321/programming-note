## [External scripts](https://javascript.info/hello-world#external-scripts)

If we have a lot of JavaScript code, we can put it into a separate file.

Script files are attached to HTML with the `src` attribute:

```html
<script src="/path/to/script.js"></script>
```

`src="script.js"`, just like `src="./script.js"`, would mean a file `"script.js"` in the current folder.

The benefit of a separate file is that the browser will download it and store it in its [cache](https://en.wikipedia.org/wiki/Web_cache).

- If `src` is set, the script content is ignored.
```html
<script _src_="file.js">
alert(1); // the content is ignored, because src is set 
</script>
```

