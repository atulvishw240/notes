
>State should not be mutated. Always use the `setState` function to change state.

State aren't like regular JS variables but more like a snapshot. Setting it does not change the state variable you have, but instead triggers a re-render. 

## How state updates

State updates are asynchronous (at a later time). Whenever you call the `setState` function, React will apply the update in the **next** component render.

Remember, state variables aren't reactive; the component is. This can be understood by the fact that calling `setState` re-renders the entire component instead of just changing the state variable on the fly.

>Setting state only changes it for the next render.

>[!important] A state variable's value never changes within a render, even if its event handler's code is asynchronous.


## State as a Snapshot Recap

- React stores state outside of your component, as if on a shelf.
- When you call `useState`, React gives you a snapshot of the state for that render.
- Variables and event handlers don't "survive" re-renders. Every render has its own event handlers.

---

## Choosing the State Structure

1. Group related 