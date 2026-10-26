# Undo Game

A small star-collecting puzzle game where every move can be undone and redone, built on **stacks**.

**Live demo:** _paste your GitHub Pages link here_

## DSA concept: Stack (LIFO)

The most recent move is always the first one you want to take back, which is last-in, first-out. The game keeps two stacks:

- **Undo stack:** every move is pushed here. Each entry stores the direction and whether the move collected a star.
- **Redo stack:** when you undo, the move is popped from the undo stack and pushed here. Making a brand new move clears it.

| Action | Stack work | Time |
|--------|------------|------|
| Move | `push` the move onto the undo stack, clear the redo stack | O(1) |
| Undo | `pop` from undo, reverse it (step back, restore the star), `push` onto redo | O(1) |
| Redo | `pop` from redo, apply it again, `push` onto undo | O(1) |
| Moves counter | `size` of the undo stack | O(1) |

Because each record knows how to reverse itself, undo never has to replay the game from the start.

## Features
- 3 levels with walls and stars
- Arrow keys or WASD to move, U to undo, R to redo, plus on-screen buttons
- Live view of the undo stack and redo stack

## Run it
Open `index.html` in a browser. No install or build step.

## Tech
HTML, CSS, and vanilla JavaScript in a single file.
