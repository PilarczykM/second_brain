---
date created: 2023-08-29 12:42
date updated: 2023-08-29 12:42
tags:
  - '#hooks'
  - '#react'
  - '#state_management'
  - '#useState'
---

#hooks #react #state_management #useState

#useState is a React Hook that lets you add a [state variable](https://react.dev/learn/state-a-components-memory) to your component.

### Snippet:

```tsx
const [state, setState] = useState(initialState);
```

### Ex:

```tsx
"use client";

import { useState } from "react";

const Counter = () => {
  const [counter, setCounter] = useState(0);
  const handleClick = () => {
    setCounter((c) => c + 1);
  };

  return (
    <>
      <button onClick={handleClick}>Clicked me ${counter}</button>
    </>
  );
};
```
