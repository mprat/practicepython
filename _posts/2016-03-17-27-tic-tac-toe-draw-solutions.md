---
layout: post
number: 27
chili: 2
categories: [solution]
part: 3
of: 4
part_text: Tic Tac Toe
---

{% include parts_sentence.md part=page.part part_text=page.part_text part_of=page.of %}

In a [previous exercise]({{ site.baseurl }}{% post_url 2015-11-16-26-check-tic-tac-toe %}) we explored the idea of using a list of lists as a "data structure" to store information about a tic tac toe game. In a tic tac toe game, the "game server" needs to know where the `X`s and `O`s are in the board, to know whether player 1 or player 2 (or whoever is `X` and `O` won).

There has also been an exercise about [drawing the actual tic tac toe gameboard]({{ site.baseurl }}{% post_url 2014-12-27-24-draw-a-game-board %}) using text characters.

The next logical step is to deal with handling user input. When a player (say player 1, who is `X`) wants to place an `X` on the screen, they can't just click on a terminal. So we are going to approximate this clicking simply by asking the user for a coordinate of where they want to place their piece.

As a reminder, our tic tac toe game is really a list of lists. The game starts out with an empty game board like this: 

{% highlight python %}
game = [[0, 0, 0],
	[0, 0, 0],
	[0, 0, 0]]
{% endhighlight %}

The computer asks Player 1 (X) what their move is (in the format `row,col`), and say they type `1,3`. Then the game would print out

{% highlight python %}
game = [[0, 0, X],
	[0, 0, 0],
	[0, 0, 0]]
{% endhighlight %}

And ask Player 2 for their move, printing an `O` in that place.

Things to note:

* For this exercise, assume that player 1 (the first player to move) will always be `X` and player 2 (the second player) will always be `O`.
* Notice how in the example I gave coordinates for where I want to move starting from (1, 1) instead of (0, 0). To people who don't program, starting to count at 0 is a strange concept, so it is better for the user experience if the row counts and column counts start at 1. This is not required, but whichever way you choose to implement this, it should be explained to the player.
* Ask the user to enter coordinates in the form "row,col" - a number, then a comma, then a number. Then you can use your Python skills to figure out which row and column they want their piece to be in.
* Don't worry about checking whether someone won the game, but if a player tries to put a piece in a game position where there already is another piece, do not allow the piece to go there. 

Bonus:

* For the "standard" exercise, don't worry about "ending" the game - no need to keep track of how many squares are full. In a bonus version, keep track of how many squares are full and automatically stop asking for moves when there are no more valid moves.

## Sample solutions

Here is one solution that does not fully complete the exercise, but gives a bit of food for thought. The `drawboard` function is a general function that can be used to draw the game board with any given inputs.

<script src="https://gist.github.com/Sreekaanth91/70c64445c214ca9df8ed.js"></script>

Another solution uses lots of functions, and also checks whether the game has ended!

<script src="https://gist.github.com/cazyw/c2f8d6b4934b2e414055.js"></script>

This solution adds some bonus functions, like checking for a winner! 

<script src="https://gist.github.com/maze88/effa1a7ce480c0e54ccf.js"></script>


Happy hacking!