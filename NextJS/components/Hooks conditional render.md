#react #useState #useEffect

Whenever you want's to render component which contains #useState , #useEffect or any #hooks and there is render condition, you need to put hooks before if statement.

Without that you violates `react-hooks/rules-of-hooks`

`React Hook "useState" is called conditionally. React Hooks must be called in the exact same order in every component render.`

### BAD:

```tsx
import { useState } from "react"
export default function ProductCard({ id }) {
	if(!id) {
		return "No id provided";
	}
	const [something, setSomething] = useState("something") // Error occured here
	return <section>{ /* Product card */ }</section>
}
```

### Good:

```tsx
import { useState } from "react"
export default function ProductCard({ id }) {
	const [something, setSomething] = useState("something") // No error
	return (
		<section>
			{ !id
				? "No id provided"
				: {
					/* Product card */
				}}
		</section>
	)
}
```
