#useState #useEffect
#DRY #customHook are reusable functions.

When you have component logic that needs to be used by multiple components, we can extract that logic to a custom Hook.

### E.g

``` tsx
"use client"

import { useState, useEffect } from "react"

const useWindowSize = () => {
 const [windowSize, setWindowSize] = useState(0)

 useEffect(() => {
  const handleWindowSizeChange = () => {
   setWindowSize(window.innerWidth)
  }
  window.addEventListener("resize", handleWindowSizeChange)
 
  return () => {
   window.removeEventListener("resize", handleWindowSizeChange)
  }
 return windowSize
}, [])

export function ExampleComponent1() {
 const windowSize = useWindowSize()
 return <p>Component 1, window size: {windowSize}</p>
}

export function ExampleComponent2() {
 const windowSize = useWindowSize()
 return <p>Component 2, window size: {windowSize}</p>
}
```
