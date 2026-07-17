
```js
function ListItem({ item }) {
  return <li>{item}</li>
}

function List({ items }) {
  return (
    <ul>
      { items.map(item => <ListItem item={item} />) }
    </ul>
  );
}

export default function App() {
  const animals = ['Lion', 'Cow', 'Snake', 'Lizard'];
  return (
    <div>
      <h1>Animals: </h1>
      <List items={animals} />
    </div>
  );
}
```

