#hooks #react #state_management #useState 

#useState is a React Hook that lets you add a [state variable](https://react.dev/learn/state-a-components-memory) to your component.


### Snipit:
```tsx
const [state, setState] = useState(initialState);
```
### Ex:

```tsx
"use client"

import {useState} from "react"

const Counter = () => {
const [counter, setCounter] = useState(0)

const handleClick = () => {
	setCounter(c => c+1)
}

return (
	<>
		<button onClick={handleClick}>Clicked me ${counter}</button>
	</>
)
}
```