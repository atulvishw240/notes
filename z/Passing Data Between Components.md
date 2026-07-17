
>[!question] How to pass data between components?
>In React, data is transferred from parent components to child components via props. This data transfer is unidirectional, meaning it flows in only one direction.

>React component functions accept a single argument, a `props` object.

Usually you don't need the whole `props` object itself, so you destructure it into individual props.

```js
function Button({ text = "Click Me!", color = "blue", fontSize = 12, handleClick }) {
  const buttonStyle = {
    color: color,
    fontSize: fontSize + "px"
  };

  return <button onClick={handleClick} style={buttonStyle}>{text}</button>;
}

export default function App() {
  const handleButtonClick = (url) => {
    window.location.href = url;
  };

  return (
    <div>
      <Button handleClick={() => handleButtonClick("https://www.google.com")} />
    </div>
  );
}
```

You can pass any JavaScript value through props, including objects, arrays, and functions.

