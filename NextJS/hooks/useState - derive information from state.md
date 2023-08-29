#useState #react #hooks

[[useState]]
Updating component value using #useState does not always needs #useEffect
In most cases you just need to use value from #useState because JS is reading from up to bottom.

### E.g

``` tsx
"use client"

import { useState } from "react"

const PRICE_PER_ITEM = 5;
export default function Cart() {
 const [quentity, setQuantity] = useState(1)
 const totalPrice = quentity * PRICE_PER_ITEM // You don't need useEffect to update property value.
 
 const handleClick = () => {
  setQuantity(prev => prev + 1)
 }

 return (
  <div>
   <button onClick={handleClick}>Add 1</button>
   <p>Total price: {totalPrice}</p>
  </div>
 )
}
```
