
- Should ship keep track of their position or let the board handle that?
- I think ship shouldn't keep track of its position and let the board handle that because tracking which ship is where should be Board's job and we will display ships on Board, so board should know where ships are placed.

- [x] Gameboards should be able to place ships at specific coordinates by calling the ship factory or class.

```js
board.place(ship, coordinates, axis)
```

---
`receiveAttack` function:
- input - coordinates
- determines whether or not the attack hit a ship
- sends 'hit' function to the correct ship or records the coordinates of the missed shot
- What about hits? I need to track those to display them differently

```js
board.receiveAttack(coordinates)
```

