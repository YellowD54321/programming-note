# Grid

## [CSS Grid Layout Module](https://www.w3schools.com/css/css_grid.asp)
The CSS Grid Layout Module offers a grid-based layout system, with rows and columns, making it easier to design web pages without having to use floats and positioning.

`display: grid;`

properties:
`grid-template-columns: // how many columns you need.`
`grid-template-rows: // how many rows you need.`
`grid-gap: //space between each grid.`

`grid-auto-flow: row; // default setting. follow rows to set up content.`
`grid-auto-flow: dense; // things would be fit in the blank.`

ex: 
```
grid-template-columns: 100px auto 150px;
grid-template-rows: 50px 50px;
grid-gap: 3px;
```
it would make a container with 3 columns , 2 rows and 3px space between each grid.

short hand method:
```
grid-template: repeat(2, 50px) / repeat(3, 1fr);
```
means
```
grid-template-columns: repeat(3, 1fr);
grid-template-rows: repeat(2, 50px);
```

---
## [fr](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Basic_Concepts_of_Grid_Layout#the_fr_unit)
Tracks can be defined using any length unit. Grid also introduces an additional length unit to help us create flexible grid tracks. The new `fr` unit represents a `fraction` of the available space in the grid container. The next grid definition would create three equal width tracks that grow and shrink according to the available space.



---
## [column line / row line](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Line-based_Placement_with_CSS_Grid)
`-1` means the final line of column or row.


---
## [grid-area](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-area)

```
...

grid-template-areas:
	"h h h h h h h h h h h h"
	
	"m c c c c c c c c c c c"
	
	"f f f f f f f f f f f f";
}

.header {
	grid-area: h;
}

.menu {
	grid-area: m;
}

.content {
	grid-area: c;
}

.footer {
	grid-area: f;
}
```
it will just fit.
- `they're ectangle'

---
