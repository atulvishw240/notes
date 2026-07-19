
React says that `UI = f(state)`

>**State** is a component's memory

>[!question] How does state work in React?
>When a component's state or props change, React runs your component function again from the beginning to figure out what should be displayed based on the freshly-set state and props. All the calculated changes are then applied to the DOM (committed). That is, the entire component is recreated, in a sense, but this time the latest state value will be returned from `useState`. This process is called **rerendering**.


**React reconcilation algorithm**
The process of rerendering generates a new virtual DOM (Document Object Model) tree. The virtual DOM is a lightweight representation of the actual DOM that React uses to keep track of the current state of the UI. React then compares the new virtual DOM tree to the previous one and calculates the minimal set of changes needed to update the actual DOM. This is the reconciliation algorithm.

## Hooks

Hooks are functions that let you use React features. All hooks are recognizable by the `use` prefix.

**Hooks rules**:
1. Hooks can only be called from the top level of a functional component.
2. Hooks can’t be called from inside loops, conditions or other nested functions.

## useState hook

It provides two things:
1. A **state variable** to retain the data between renders.
2. A **state setter function** to update the variable and trigger React to render the component again.

>State is local to a component instance on the screen. If you **render the same component twice, each copy will have completely isolated state!**


