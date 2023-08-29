#hooks #react #state-management #useState

#useState useState is a React Hook that lets you add a [state variable](https://react.dev/learn/state-a-components-memory) to your component.

The **best approach** is to pass previous state `setCounter((prev) => prev + 1)`

### Snippet

```tsx
const [state, setState] = useState(initialState);
```

### E.g

```tsx
"use client";

import { useState } from "react";

const Counter = () => {
  const [counter, setCounter] = useState(0);
  const handleClick = () => {
    setCounter((c) => c + 1);
  };

  return <button onClick={handleClick}>Clicked me ${counter}</button>;
};
```
