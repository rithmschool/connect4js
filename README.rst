Connect Four
============

In this exercise, you plan & help code a Connect Four game in Javascript.


The Game
--------

Connect Four is played on a grid, 7 wide by 6 deep, with two players,
1 (red) and 2 (blue). The players alternate turns, dropping a piece of their
color in the top of a column. The piece will fall down to the further-down
unoccupied slot.

The game is won when a player makes four in a row (horizontally, vertically,
or diagonally). The game is a tie if the entire board fills up without a
winner.

Step One: Planning
------------------

Take a few minutes to think about how you would build a game like this
using HTML/JS/CSS and jQuery:

- what HTML would be useful for the game board itself?

- how could you represent a played-piece in the HTML board?

- in the JavaScript, what would be a good structure for the in-memory game board?

- what might the flow of the game be?

Then, write down some functions names/descriptions that would be useful
for this game.

Step Two: HTML
--------------

Take a look at the starting HTML provided, ``index.html``. There are several **TODO**
comments of changes to make to use the starter CSS/JS and to bring in jQuery.

Step Three: makeBoard
---------------------

The `makeBoard` function needs to be implemented. It should set the global
`board` variable to be an array of 6 arrays (height), each containing 7 items
(width).

You *could* do this like::

    array = [ 
      [ null, null, null, null, null, null, null ],
      [ null, null, null, null, null, null, null ],
      [ null, null, null, null, null, null, null ],
      [ null, null, null, null, null, null, null ],
      [ null, null, null, null, null, null, null ],
      [ null, null, null, null, null, null, null ],
    ]

However, it's far better to make the game flexible about the height and width of
the board and use the `WIDTH` and `HEIGHT` constants in `connect4.js`. Implement
this function to make this board dynamically.

Step Four: makeHTMLBoard
------------------------

This function is missing the first line, that gets the `board` variable. Fix this.

Add comments to the code that dynamically creates the HTML table.

Step Five: placeInTable & Piece CSS
-----------------------------------

This function should add a `div` inside the correct `td` cell in the HTML game
board. This div should have the `piece` class on it, and should have a class
for whether the current player is 1 or 2, like `p1` or `p2`.

Update the CSS file to:

- make the piece `div` round, not square

- be different colors depending on whether it's a player #1 or #2 piece

Step Six: handleClick
---------------------

There are several pieces to write/fix here:

- this never updates the `board` variable with the player #. Fix.

- add a check for "is the entire board filled" [hint: the JS `every` method
  on arrays would be especially nice here!]

- add code to switch `currPlayer` between 1 and 2

Step Seven: findSpotForCol
--------------------------

Right now, the game drops always drops a piece to the bottom of the column,
even if a piece is already there. Fix this function so that it finds the
lowest empty spot in the game board and returns the y coordinate (or
`null` if the column is filled).

Step Eight: CELEBRATE!
----------------------

If you got this far, you should have a fully functional Connect Four game.
Congratulations!

Optional Step Nine: Read & Comment checkForWin
----------------------------------------------

The `checkForWin` function is already written, but it needs comments to help
explain how it works. Add some!

Also, this is a good strategy for finding a winner, but it's not the most
efficient. Later, you may learn ways to find winners that don't keep
re-checking the same area of the board [using techniques for "dynamic
programming", you can make this code more efficient, though it's much more
advanced than the rest of this exercise. You can come back to this code
much later!]

Optional Step Ten: Add Animation!
---------------------------------

jQuery includes animation features (Read their docs!). If you change the
`.piece` divs to be positioned absolutely, you can animate the `top` CSS
property to animate the pieces so they appear to drop down. This is tricky,
but will give you a chance to play with jQuery animations, as well as 
working with relative/absolute positioning.


