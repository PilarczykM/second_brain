The #useEffect  hook allows you to perform side effects in your components.

>Some examples of side effects are: fetching data, directly updating the DOM, and timers.

### E.g

#useState #useEffect #setInterval

``` tsx
"use client"

import { useState, useEffect } from "react"

export const function CounterExample() {
 const [count, setCount] = useState(0)

 useEffect(() => {
  const id = setInterval(() => {
   console.log("Interval function running")
   setCount(prev => prev + 1)
   /* Without passing prev, because of the clouser
   we would only get 'count' once which would has always value equals to 0. 
   So each time set interval executes you will see 0 + 1.
   By passing prev react always gets the most updated value. */
  })

  return () => { clearInterval(id) } // <-- On component unmount you can clear some connections / intervals
 }, []) // <-- Only on component mount dependency array
}
```
