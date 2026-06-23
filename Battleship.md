
`receiveAttack` function:
- input - coordinates
- determines whether or not the attack hit a ship
- sends 'hit' function to the correct ship or records the coordinates of the missed shot
- What about hits? I need to track those to display them differently

```js
board.receiveAttack(coordinates)
```


---

## 19 June

**Ship**
- [x] properties - length, number of times hit, isSunk
- [x] Methods - 
	- [x] `hit()` that increase number of hits
	- [x] `isSunk()` calculates whether a ship is sunk

**GameBoard**
- [x] Know your code is working fine by running the tests, don't rely on `console.log` or DOM methods
- [x] Place your ships on Board
- [x] Receive Attack on a ship and send `hit()` method to that ship. Record the shot as miss if it doesn't hit a ship
- [x] GameBoard should be able to keep track of missed attacks
- [x] report whether all ships have been sunk

**Player**
- [x] Each player has a name and its own gameboard

**DisplayController** (manage actions that happen in the DOM)
- [x] You can begin crafting your User Interface
- [ ] Set up a new game by creating Players. For now just populate each player's Gameboard with pre-determined coordinates.
- [ ] HTML implementation should display both player's boards and render them using information from the **GameBoard**
- [ ] For attacks, let user click on a coordinate in the enemy Gameboard. Send the user input to methods on your objects, and re-render the boards to display the new information.
	- [ ] Players take alternate turns. Keep track of player's turn here in this module
	- [ ] Game played against computer, so make sure computer makes a random legal move. (don't make same move twice)
- [ ] Game ends when all ships of one player's has been sunk
- [ ] Implement a system that allow players to place their ships by a button to cycle through random placements.


