
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

You can nest your components like regular html elements.

```
<Card>
  <Avatar />
</Card>
```

```js
function Card({ children }) {
  return (
    <div className="card">
      <div className="card-content">
        {children}
      </div>
    </div>
  );
}

export default function Profile() {
  return (
    <div>
      <Card>
        <h1>Photo</h1>
        <img
          className="avatar"
          src="https://react.dev/images/docs/scientists/OKS67lhm.jpg"
          alt="Aklilu Lemma"
          width={70}
          height={70}
        />
      </Card>
      <Card>
        <h1>About</h1>
        <p>Aklilu Lemma was a distinguised engineer</p>
      </Card>
    </div>
  );
}
```


>props are **immutable**. When a component needs to change its props, it will have to "ask" its parent component to pass it *different props* - a new object!. 



