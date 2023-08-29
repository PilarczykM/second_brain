#react #useState #hooks 

[[useState]]
A common mistake when working with objects is a bad update. #object non-primitive value containing properties (with different type)

To properly update object within #useState remember to use #spread-operator on rest values.

Of course you also can upgrade `handleChange` function to handle multiple inputs by simply extracting name from event `[e.target.name]: e.target.value`

### E.g

```tsx
"use client";

import { useState } from "react";

export default function User() {
  const [user, setUser] = useState({ name: "", city: "", age: 25 });
  const handleChange = (e) => {
    setUser((prev) => ({
      // user is an object, so remember to return {}
      ...prev,
      [e.target.name]: e.target.value,
    }));
  };

  return (
    <form>
      <input type="text" name="name" onChange={handleChange} />
      <input type="text" name="city" onChange={handleChange} />
    </form>
  );
}
```
