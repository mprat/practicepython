---
layout: post
number: 27
chili: 2
categories: [exercise]
published: True
---

## Exercise

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

## Concepts

One review concept that is definitely needed (in addition to the [user input]({{ site.baseurl }}{% post_url 2014-01-29-01-character-input %}) that is the core of the exercise) is the need to "split" strings. 

The user will input coordinates in the form "row,col", which `input()` will then read in as a string. But we really want the numbers that come out of that string, to know which row and column to place the piece at.

One approach is to use the idea of [strings as lists]({{ site.baseurl }}{% post_url 2014-03-12-06-string-lists %}) to extract the row and column numbers. This works great if your row and column numbers are always single digits - the row will always be at index 0 and the column will always be at index 2. But this breaks when the numbers are larger than one digit (I know, not going to happen in tic tac toe, but it's easy to image extending this to other games).

Instead, there are two string manipulation functions that will help you: 

1. [`.split()`](https://docs.python.org/2/library/string.html#string.split) - Takes a string and returns a list, using the separator as the split criteria. So if you have a string `name = "John Doe"` and do `name_list = name.split(" ")`, `name_list` will be `["John", "Doe"]`. You can use any separator / split character you want. Just remember, that each of the elements returned back will be a string as well.
2. [`.strip()`](https://docs.python.org/2/library/string.html#string.strip) - Takes a string and removes the whitespace on the left and right sides of it. So you have a string `name = "     Michele "`, and you do `name = name.strip()`, and now `name` will just be `"Michele"` - nice and clean.

I challenge you to figure out how to use them in the exercise!

Happy Coding!

{% include submit.md %}