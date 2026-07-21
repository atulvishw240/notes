
React says that `UI = f(state)`

>**State** is a component's memory. It is local to a component instance on the screen. If you **render the same component twice, each copy will have completely isolated state!**

To use state in React we use `useState` [[hook]]. 

## useState hook

It provides two things:
1. A **state variable** to retain the data between renders.
2. A **state setter function** to update the variable and trigger React to render the component again.


>[!question] How does state work in React?
>When a component's state or props change, React runs your component function again from the beginning to figure out what should be displayed based on the freshly-set state and props. All the calculated changes are then applied to the DOM (committed). That is, the entire component is recreated, in a sense, but this time the latest state value will be returned from `useState`. This process is called **re-rendering**.


**React reconcilation algorithm**
The process of rerendering generates a new virtual DOM (Document Object Model) tree. The virtual DOM is a lightweight representation of the actual DOM that React uses to keep track of the current state of the UI. React then compares the new virtual DOM tree to the previous one and calculates the minimal set of changes needed to update the actual DOM. This is the reconciliation algorithm.

---

## Render and Commit

1. **Triggering** a render (delivering the guest’s order to the kitchen)
2. **Rendering** the component (preparing the order in the kitchen)
3. **Committing** to the DOM (placing the order on the table)

Updating your component's state automatically queues a render. **"Rendering" is React calling your components.**

- **On initial render,** React will call the root component.
- **For subsequent renders,** React will call the function component whose state update triggered the render.

After rendering (calling) your components, React will modify the DOM.

- **For the initial render,** React will use the [`appendChild()`](https://developer.mozilla.org/docs/Web/API/Node/appendChild) DOM API to put all the DOM nodes it has created on screen.
- **For re-renders,** React will apply the minimal necessary operations (calculated while rendering!) to make the DOM match the latest rendering output.


