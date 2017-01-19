---
layout: post
number: 32
chili: 2
part: 3
of: 3
part_text: Hangman
categories: [solution]
---

{% include solution_header.md number=page.number %}

{% include parts_sentence.md part=page.part part_text=page.part_text part_of=page.of %} 

_You can start your Python journey anywhere, but to finish this exercise you will have to have finished Parts 1 and 2._

In this exercise, we will finish building Hangman. In the game of Hangman, the player only has 6 incorrect guesses (head, body, 2 legs, and 2 arms) before they lose the game.

In Part 1, we loaded a random word list and picked a word from it. In Part 2, we wrote the logic for guessing the letter and displaying that information to the user. In this exercise, we have to put it all together and add logic for handling guesses.

Copy your code from Parts 1 and 2 into a new file as a starting point. Now add the following features:

* Only let the user guess 6 times, and tell the user how many guesses they have left.
* Keep track of the letters the user guessed. If the user guesses a letter they already guessed, don't penalize them - let them guess again.

Optional additions:

* When the player wins or loses, let them start a new game.
* Rather than telling the user `"You have 4 incorrect guesses left"`, display some picture art for the Hangman. _This is challenging - do the other parts of the exercise first!_

Your solution will be a lot cleaner if you make use of functions to help you!

## Sample Solution

Here is a sample solution from a reader that uses the solutions to Parts 1 and 2, and just puts them on one file:

<script src="https://gist.github.com/anonymous/8ed14085c77095e106c79952be5588cf.js"></script>

And here's my solution, making more heavy use of functions:

<script src="https://gist.github.com/mprat/ed31902d422353bc572ae8b335150f6c.js"></script>
