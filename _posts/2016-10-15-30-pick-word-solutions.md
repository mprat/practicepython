---
layout: post
number: 30
chili: 2
categories: [solution]
published: true
---

## [Exercise {{ page.number }}]({{ site.baseurl }}{% post_url 2016-09-24-30-pick-word %})

_This exercise is Part 1 of 3 of the Hangman exercise series. The other 2 exercises are: [Part 2]({{ site.baseurl }}{% post_url 2017-01-02-31-guess-letters %}) and [Part 3]({{ site.baseurl }}/exercise/comingsoon)._

In this exercise, the task is to write a function that picks a random word from a list of words from the [SOWPODS dictionary](http://norvig.com/ngrams/sowpods.txt). Download this file and save it in the same directory as your Python code. This file is [Peter Norvig](https://en.wikipedia.org/wiki/Peter_Norvig)'s compilation of the dictionary of words used in professional Scrabble tournaments. Each line in the file contains a single word.

_Hint: use the Python `random` library for picking a random word._

## Sample solution

To solve this exercise, you need to do three things:

1. Read all the lists of words
2. Generate a random number
3. Take that word

Here is a sample solution:

<script src="https://gist.github.com/coderunner007/0f9a2bc3c45f70979fba09666ef3dc2e.js"></script>

Here is an alternate approach, with some comments:

{% highlight python %}
  # import the random library
  import random

  # read all the list of words
  words = []
  with open('sowpods.txt', 'r') as f:
    line = f.readline().strip()
    words.append(line)
    while line:
      line = f.readline().strip()
      words.append(line)

  # generate a random number
  random_index = random.randint(0, len(words))

  # take the word
  print("Random word: ", words[random_index])
{% endhighlight %}

There are many solutions to every problem. Enjoy hacking around to find another solution!
