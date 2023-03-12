# component

In JSX, something  inside ``{}`` means it's JavaScript syntax.

As HTML only use ``string``, using ``{}`` to pass property to destinaion as it's original type.

ex:
```
<Card

	img="katie-zaferes.png"
	
	rating="5.0"
	
	reviewCount={6}
	
	country="USA"
	
	title="Life Lessons with Katie Zaferes"
	
	price={136}

/>
```

it will pass an object to ``Card`` component, which is:
```
{
	img: "katie-zaferes.png",
	
	rating: "5.0",
	
	reviewCount: 6,
	
	country: "USA",
	
	title: "Life Lessons with Katie Zaferes",
	
	price: 136;
}
```

