---
layout: post
number: 31
chili: 2
part: 2
of: 3
part_text: Hangman
categories: [exercise]
---

{% include exercise_header.md number=page.number %}

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

Happy Coding!

{% include submit.md %}
