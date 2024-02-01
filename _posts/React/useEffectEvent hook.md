# useEffectEvent (Experimental)

### Today I have come across a new hook in react which lets you to run some code using reactives(props, state) without re-rendering on reactives change.

What if you want to log a new page visit after every url change, but not if only the shoppingCart changes? You can’t exclude shoppingCart from dependencies without breaking the reactivity rules. However, you can express that you don’t want a piece of code to “react” to changes even though it is called from inside an Effect. Declare an Effect Event with the useEffectEvent Hook, and move the code reading shoppingCart inside of it:

```
function Page({ url, shoppingCart }) {
  const onVisit = useEffectEvent(visitedUrl => {
    logVisit(visitedUrl, shoppingCart.length)
  });

  useEffect(() => {
    onVisit(url);
  }, [url]); // ✅ All dependencies declared
  // ...
}
```
