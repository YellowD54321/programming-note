# Selector

- Element selector
- Class selector
- ID selector
- attribute selector

## Element selector
Simply write the element's tag, without the <>
ex:
```
body{
	background-color:#333;
	color: #f4f4f4;
}
```
 ```
a {
	color: darksalmon;
}
```

## Class selector
A class is a group.

Classes are a type of attribute we can add to an HTML element.
ex:
```
<p class="intro"> ... </p>
```

In CSS, the class attribute is referenced by using a full stop.
ex:
```
.intro {
	font-size: 18px;
	color: #2b5dad;
}
```

The element before the classname is able to but not neccessary and not recommended.
ex:
```
p.intro {
	font-size: 18px;
	color: #2b5dad;
}
```

## ID selector
ID is an indiviudal.

IDs are a type of attribute we can add to an HTML element.
ex:
```
<p id="intro">...</P>
```

An ID is represented by a hashtag
ex:
```
#intro {
	font-size: 18px;
	color: #2b5dad;
}
```

ID vs Class
- An ID can only be used one time per page.
- A class can be used over and over again.
- ID will overwrite a class if they are both selecting the same thing.
ex:
```
<p class="paragraph1" id="intro">...</P>
```
only *\#intro* will works.

---
## attribute selector
`[attr=value]`
```css
[type='radio'] {
  margin: 20px 0px 20px 0px;
}
```

![[Pasted image 20221109231534.png]]