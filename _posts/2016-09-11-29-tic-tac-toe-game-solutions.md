---
layout: post
number: 29
chili: 3
categories: [solution]
---

## [Exercise {{ page.number }}]({{ site.baseurl }}{% post_url 2016-08-03-29-tic-tac-toe-game %})

In 3 previous exercises, we built up a few components needed to build a Tic Tac Toe game in Python:

1. [Draw the Tic Tac Toe game board]({{ site.baseurl }}{% post_url 2014-12-27-24-draw-a-game-board %})
2. [Checking whether a game board has a winner]({{ site.baseurl }}{% post_url 2015-11-16-26-check-tic-tac-toe %})
3. [Handle a player move from user input]({{ site.baseurl }}{% post_url 2015-11-26-27-tic-tac-toe-draw %})

The next step is to put all these three components together to make a two-player Tic Tac Toe game!

## Sample solution

This exercise is unique because it relies on the output of the other exercises that need to be put together to make the final solution. The goal is to get practice with functions and how they work together in larger programs.

The 3 exercises above suggest breaking your Tic Tac Toe game into (at least) 4 functions:

1. A function for drawing the game board (and the location of pieces)
2. A function for checking whether there is a winner in the game
3. A function for adding user input into the game state
4. A main function that calls the others and plays the game

The way to solve this problem is to look back at all 3 solutions to the previous exercises, copy them into one file, and modify what you had before. This is a different way of coding than coding an entire program from scratch, and can often save a lot of time.

For my solution, I decided to copy all the functions from the older exercises into one file, and work from the main game logic from [Part 3]({{ site.baseurl }}{% post_url 2015-11-26-27-tic-tac-toe-draw %}). Part 3 almost made you write the entire game - the main loop asking users for positions and input is already there, so starting from that point and modifying will let you finish this exercise in 30 minutes!

Here is what my code looks like after copying in my solutions to [Part 1]({{ site.baseurl }}{% post_url 2014-12-27-24-draw-a-game-board %}), [Part 2]({{ site.baseurl }}{% post_url 2015-11-16-26-check-tic-tac-toe %}), and [Part 3]({{ site.baseurl }}{% post_url 2015-11-26-27-tic-tac-toe-draw %}) of this exercise:

<script src="https://gist.github.com/mprat/8783e0b4b3eba243ca125a522f4e0ac9.js"></script>

After some modifications:

* to the game board drawing functions
* adding a function to check the availability of a square
* adding a function to check whether there are any moves available
* updating the main game loop end condition

The final product is here:

<script src="https://gist.github.com/mprat/921095c93cdaa4f0a8cfcc131f261f1d.js"></script>

Happy hacking!