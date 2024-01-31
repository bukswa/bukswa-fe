# New hooks in react to improve productivity and performance

## use

Unlike all other React Hooks, use can be called within loops and conditional statements like if. 
Like other React Hooks, the function that calls use must be a Component or Hook.

Call use in your component to read the value of a resource like a Promise or context.

```
import { use } from 'react';

function MessageComponent({ messagePromise }) {
  const message = use(messagePromise);
  const theme = use(ThemeContext);
  // ...
```

Unlike useContext, use can be called in conditionals and loops like if.

```
function HorizontalRule({ show }) {
  if (show) {
    const theme = use(ThemeContext);
    return <hr className={theme} />;
  }
  return false;
}
```
<a href="https://react.dev/reference/react/use" > More Reading </a>

----

## useDeferredValue

`useDeferredValue` is a React Hook that lets you defer updating a part of the UI.

A common alternative UI pattern is to defer updating the list of results and to keep showing the previous results until the new results are ready. 
Call `useDeferredValue` to pass a deferred version of the query down:

```
export default function App() {
  const [query, setQuery] = useState('');
  const deferredQuery = useDeferredValue(query);
  return (
    <>
      <label>
        Search albums:
        <input value={query} onChange={e => setQuery(e.target.value)} />
      </label>
      <Suspense fallback={<h2>Loading...</h2>}>
        <SearchResults query={deferredQuery} />
      </Suspense>
    </>
  );
}
```

The query will update immediately, so the input will display the new value. 
However, the `deferredQuery` will keep its previous value until the data has loaded, so SearchResults will show the stale results for a bit.



