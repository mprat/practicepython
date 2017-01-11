---
layout: post
number: 29
chili: 3
categories: [exercise]
published: True
part: 4
of: 4
part_text: Tic Tac Toe
---

## Exercise {{ page.number }} (and [Solution]({{ site.baseurl }}{% post_url 2016-09-11-29-tic-tac-toe-game-solutions %}))

{% include parts_sentence.md part=page.part part_text=page.part_text part_of=page.of %}

In 3 previous exercises, we built up a few components needed to build a Tic Tac Toe game in Python:

1. [Draw the Tic Tac Toe game board]({{ site.baseurl }}{% post_url 2014-12-27-24-draw-a-game-board %})
2. [Checking whether a game board has a winner]({{ site.baseurl }}{% post_url 2015-11-16-26-check-tic-tac-toe %})
3. [Handle a player move from user input]({{ site.baseurl }}{% post_url 2015-11-26-27-tic-tac-toe-draw %})

The next step is to put all these three components together to make a two-player Tic Tac Toe game! Your challenge in this exercise is to use the functions from those previous exercises all together in the same program to make a two-player game that you can play with a friend. There are a lot of choices you will have to make when completing this exercise, so you can go as far or as little as you want with it.

Here are a few things to keep in mind:

* You should keep track of who won - if there is a winner, show a congratulatory message on the screen.
* If there are no more moves left, don't ask for the next player's move!

As a bonus, you can ask the players if they want to play again and keep a running tally of who won more - Player 1 or Player 2.

# Tips

_Starting this exercise from scratch will take you longer than 30 minutes. The best way to save time is to reuse work that has already been done!_

Because you have already done the work of the previous 3 exercises, no need to re-do them all! Simply take your code from those exercises, copy it into a new file, and start again. Even if you lost your code from those exercises, go to the solutions pages, [here]({{ site.baseurl }}{% post_url 2014-12-27-24-draw-a-game-board %}), [here]({{ site.baseurl }}{% post_url 2015-11-16-26-check-tic-tac-toe %}), and [here]({{ site.baseurl }}{% post_url 2015-11-26-27-tic-tac-toe-draw %}), pick your favorite solutions, and start from those! 

A large part of programming is reusing code written by someone else to accomplish a task. Sometimes it is fun to write a solution yourself, but other times you want to build on top of something else. This exercise gives you an opportunity to practice one of the arts of programming - starting from code someone else wrote and creating something on top of it.

## Resources

To effectively complete this exercise, you will need to make extensive use of functions to accomplish small, modular, tasks within your larger program. Here are some resources about functions in case you get stuck:

* [The PracticePython take on functions]({{ site.baseurl }}{% post_url 2014-04-16-11-check-primality-functions %})
* Learn Python the Hard Way, [exercise 19](http://learnpythonthehardway.org/book/ex19.html) and [exercise 21](http://learnpythonthehardway.org/book/ex21.html)
* Execute some basic code on [learnpython.org](http://www.learnpython.org/en/Functions)

If you are new to Python, this might be one of the longest programs you have written so far, so have fun!

Happy Coding!

{% include submit.md %}