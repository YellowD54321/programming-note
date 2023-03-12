# Flexbox

## [CSS彈性盒子用法](https://developer.mozilla.org/zh-TW/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)


```
display: flex;
```
---
### flex property:
```
.container > div {
	flex: 1; // make every div in this class spread averagely.
}
```

```
.container > .search {
	flex: 2; // make class 'search' twice width in this container.
}
```

`flex-grow // 成長`
`flex-shrink // 收縮`
`flex-basis // 基礎`

---
### [align-items property](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items):

In Flexbox, it controls the alignment of items on the [Cross Axis](https://developer.mozilla.org/en-US/docs/Glossary/Cross_Axis).

align-items - control children
align-self - control itself and override align-item

---
### [justify-content](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content)

The [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) **`justify-content`** property defines how the browser distributes space between and around content items along the [main-axis](https://developer.mozilla.org/en-US/docs/Glossary/Main_Axis) of a flex container, and the inline axis of a grid container.

---
### [order](https://www.w3schools.com/cssref/css3_pr_order.asp)

The `order` property specifies the order of a flexible item relative to the rest of the flexible items inside the same container.

**Note:** If the element is not a flexible item, the `order` property has no effect.

