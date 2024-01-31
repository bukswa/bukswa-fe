# useEffect insights

Here is a list of few questions which are not well aware by many developers.

1. Why useEffect runs 2 times in development mode?

   **Ans**: it follows `setup → cleanup → setup` sequence.  This is a stress-test that verifies your Effect’s logic is implemented correctly. If this causes visible issues, your cleanup function is missing some logic. The cleanup function should stop or undo whatever the setup function was doing.
   The rule of thumb is that the user shouldn’t be able to distinguish between the setup being called once (as in production)

2. When do we need useEffect?

      **Ans**: If you’re not trying to synchronize with some external system, <u>you probably don’t need an Effect</u>.

3. 
