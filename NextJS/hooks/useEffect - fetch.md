[[useEffect]]

Here is an example how to properly unmount component when fetch call is no longer needed.

### E.g

``` tsx
export default function Post() {
 const [id, setId] = useState(1)

 return (
  <div>
   <button onClick={() => Math.floor(Math.random() * 100)}>Show me a different post</button>
  <PostBody id={id} />
  </div>
 )
}

export function PostBody({ id } : { id: number }) {
 const [text, setText] = useState("")

 useEffect(() => {
  const controller = new AbortController() // AbortController allows to prevent from unwanted re-renders when component already unmounts.
  fetch(`https://dummyjson.com/posts/${id}`, {
   signal: controller.signal
  })
   .then(res => res.json())
   .then(data => setText(data.body))

  return () => controller.abort() // Aborting on unmount
 }, [id])
 
 return <p>{text}</p>
}
```
