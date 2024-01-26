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

#


