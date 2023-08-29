[[useState]]
#useState hook can easily handle #primitive value

``` tsx
const [price, setPrive] = useState(0) // Update price will not rerender the component.
```

However working with #non-primitive values will always rerender component, every time #react thinks while updating state you are passing completely new object, because object comperes by reference not by actual value.

``` tsx
const [item, setItem] = useState({name: "", value: 0}) // Update item will rerender the component
```

> You can prevent re-rendering by checking that every value in object consist the same.