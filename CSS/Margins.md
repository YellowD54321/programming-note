# Margins
Margins are used to control the position of an element relative to those around it.

- margin-left
- margin-right
- margin-to
- margin-bottom

maring: top right bottom left
ex:
```
margin: 10px 20px 30px 40px 
```
means: 10px for top, 20px for right, 30px for bottom, 40px for left
```
margin: 10px
```
means: 10px for all sides
```
margin: 10px 20px
```
means: 10px for top & bottom, 20px for left & right

```
margin: 10px 20px 30px
```
means: 10px for top, 20px for left & right, 30px for bottom

## auto
automatlly set margin for the side. 
*this will not work on the top and bottom to center vertically*
ex:
```
margin-left: auto;
```
```
margin: 0 auto;
```

margin = empty space
padding = more background

## default margin
browser has a default margin. which is like:
![[Pasted image 20220125234438.png]]

to avoid this default margin, using:
```
body {
	margin: 0;
}
```
then it looks like:
![[Pasted image 20220125234418.png]]