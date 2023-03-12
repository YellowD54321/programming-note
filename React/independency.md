# independency

---

### nanoid
add random id for your objects.
ex:
```
import {nanoid} from "nanoid"

...

const newDice = []
for (let i = 0; i < 10; i++) {
	newDice.push({
		value: Math.ceil(Math.random() * 6),
		id: nanoid()
	})
}

...


```


---