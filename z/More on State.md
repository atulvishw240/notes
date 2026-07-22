
>State should not be mutated. Always use the `setState` function to change state.

State aren't like regular JS variables but more like a snapshot. Setting it does not change the state variable you have, but instead triggers a re-render. 

## How state updates

State updates are asynchronous (at a later time). Whenever you call the `setState` function, React will apply the update in the **next** component render.

Remember, state variables aren't reactive; the component is. This can be understood by the fact that calling `setState` re-renders the entire component instead of just changing the state variable on the fly.

---

