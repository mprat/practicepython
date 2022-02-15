---
layout: post
number: 31
chili: 2
part: 2
of: 3
part_text: Hangman
categories: [solution]
published: true
---

{% include parts_sentence.md part=page.part part_text=page.part_text part_of=page.of %}

Let's continue building Hangman. In the game of Hangman, a clue word is given by the program that the player has to guess, letter by letter. The player guesses one letter at a time until the entire word has been guessed. (In the actual game, the player can only guess 6 letters incorrectly before losing).

Let's say the word the player has to guess is "EVAPORATE". For this exercise, write the logic that asks a player to guess a letter and displays letters in the clue word that were guessed correctly. For now, let the player guess an infinite number of times until they get the entire word. As a bonus, keep track of the letters the player guessed and display a different message if the player tries to guess that letter again. Remember to stop the game when all the letters have been guessed correctly! Don't worry about choosing a word randomly or keeping track of the number of guesses the player has remaining - we will deal with those in a future exercise.

An example interaction can look like this:

{% highlight pycon %}
>>> Welcome to Hangman!
_ _ _ _ _ _ _ _ _
>>> Guess your letter: S
Incorrect!
>>> Guess your letter: E
E _ _ _ _ _ _ _ E
...
{% endhighlight %}

And so on, until the player gets the word.

## Sample solution

To write the logic of our Hangman game, we need a few components:

1. A way to store the word in play
2. Keep track of which letters in the word have already been guessed
3. Ask the user for a letter and display the results

As a bonus, we can add the component of displaying a different message if the user has already guessed that letter.

Things to keep in mind:

* Upper-case letters and lower-case letters are not equal! When you do `'a' == 'A'` in Python, the result will be FALSE! So make sure to do all your operations in either lowercase or uppercase.
* It is much faster to check whether an element is in a set than a list. This is not important for the correctness of your program, but it is a good thing to keep in mind for when your programs become more complex.

Here is one sample solution:

<script src="https://gist.github.com/anonymous/c39e3b9db1764a3a119f6dc90905c2b2.js"></script>

The only thing I would change here is on line 9, change `lstGuessed` to a `set()`, so that on line 12, the `in` check will be very fast.

As always, play on!
