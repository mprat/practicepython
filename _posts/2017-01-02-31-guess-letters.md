---
layout: post
number: 31
chili: 2
categories: [exercise]
---

## Exercise

_This exercise is Part 2 of 3 of the Hangman exercise series. The other 2 exercises are: [Part 1]({{ site.baseurl }}{% post_url 2016-09-24-30-pick-word %}) and [Part 3]({{ site.baseurl }}/exercise/comingsoon)._

Let's continue building Hangman. In the game of Hangman, a clue word is given by the program that the player has to guess, letter by letter. The player guesses one letter at a time until the entire word has been guessed. (In the actual game, the player can only guess 6 letters incorrectly before losing).

Let's say the word the player has to guess is "EVAPORATE". For this exercise, write the logic that asks a player to guess a letter and displays letters in the clue word that were guessed correctly. For now, let the player guess an infinite number of times until they get the entire word. As a bonus, keep track of the letters the player guessed and display a different message if the player tries to guess that letter again. Remember to stop the game when all the letters have been guessed correctly! Don't worry about choosing a word randomly or keeping track of the number of guesses the player has remaining - we will deal with those in a future exercise.

An example interaction can look like this:

{% highlight pycon %}
Welcome to Hangman!
_ _ _ _ _ _ _ _ _
Guess your letter: S
Incorrect!
Guess your letter: E
E _ _ _ _ _ _ _ E
...
{% endhighlight %}

And so on, until the player gets the word.

Happy Coding!

{% include submit.md %}
