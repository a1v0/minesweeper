# Minesweeper

An HTML Canvas implementation of Minesweeper, plus eventually functionality to solve it automatically. Desktop-only.

## Plan

1. Set up Svelte, Jest, Prettier
2. Create rudimentary page wherein to store game
3. Create Node class to store all data:
   - `isMine`: Boolean
   - `isFlagged`: Boolean
   - `isVisible`: Boolean
   - Either lots of neighbour properties in graph structure, e.g. `northeastNeighbour: <reference to other Node>` or simply an integer to store the number of mine neighbours, which is calculated before the game begins
   - `coordinates`: `{ x: Int, y: Int }` to show the position of the tiles on the board
   - Static property to store amount of mines correctly flagged
4. Find out standard board sizes and how many mines per board, then create multidimensional array of all Nodes
5. Set `x` amount of nodes to be bombs in random locations
6. Populate `neighbour` field(s)
7. Create function to draw HTML canvas (named something like `renderBoard()`), with grid-style layout, using the array to define what to show and how to show it (e.g. flagged fields and such)
8. Create `onClick` method to set clicked node to visible. Then, if it's a bomb, end the game (needs a further method to do).
   - Need to figure out how to do the logic for large areas where none of the nodes have any mines as neighbours
   - Perhaps a Boolean field on the Node object to indicate whether any given node has neighbours who neighbour 0 bombs.
9. Create a right-click method to apply a flag to a field
10. Add things like a a bomb counter showing the amount of flags put onto the game, and the ability to change the board's size. Plus potentially a ticking time counter, for authenticity
