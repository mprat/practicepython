---
layout: post
number: 18
chili: 3
categories: [exercise]
---

Create a program that will play the "cows and bulls" game with the user. The game works like this:

Randomly generate a 4-digit number. Ask the user to guess a 4-digit number. For every digit that the user guessed correctly _in the correct place_, they have a "cow". For every digit the user guessed correctly _in the wrong place_ is a "bull." Every time the user makes a guess, tell them how many "cows" and "bulls" they have. Once the user guesses the correct number, the game is over. Keep track of the number of guesses the user makes throughout the game and tell the user at the end. 

Say the number generated by the computer is 1038. An example interaction could look like this: 

{% highlight pycon %}
  Welcome to the Cows and Bulls Game! 
  Enter a number: 
  >>> 1234
  2 cows, 0 bulls
  >>> 1256
  1 cow, 1 bull
  ...
{% endhighlight %}

Until the user guesses the number. 

## Concepts for this week: 

1. Randomness (we've covered this a few times before. Mainly in [a previous exercise]({{ site.baseurl }}{% post_url 2014-04-02-09-guessing-game-one %}).)
2. Functions (covered in a [previous exercise]({{ site.baseurl }}{% post_url 2014-04-16-11-check-primality-functions %}) also)
3. Main method

## Main method

Since we have covered randomness and functions, we still need to cover the idea of a "main" method. If you have programmed before, you will wonder why you haven't needed a main method so far in your Python code.

First, here is how you do it: 

{% highlight python %}
  def square(num):
    return num * num

  if __name__=="__main__":
    user_num = input("Give me a number: ")
    print(square(num))
{% endhighlight %}

Note that in both `__name__` and `__main__`, there are TWO underscore (`_`) characters.

If you run this program, it behaves as expected: asking the use for a number and printing out the square in return. However, you might be wondering - how is this different from the way we've been writing programs until this point? 

{% highlight python %}
  def square(num):
    return num * num

  user_num = input("Give me a number: ")
  print(square(num))
{% endhighlight %}

You are correct if you think the second example will have THE SAME BEHAVIOR as in the first case. At least the way we've been running Python files until this point. I will attempt to explain.

Python does not have a specified entry point like many other languages (for example, C++ always looks for a `void main()` method to run). Python files and programs are executed line by line by the Python interpreter, from however the Python file or program is run. When the definition of a function is reached by the interpreter, the function is not run, but rather loaded to be run later. (We discussed this when we talked about functions in a [previous post]({{ site.baseurl }}{% post_url 2014-04-16-11-check-primality-functions %}).) Whatever is written outside of a function will get executed immediately - this includes creating variables and calling the functions that were previously loaded.

There are (most commonly) two ways to run a Python file: 

1. "Just running it" (which you can do from the terminal, through the "Run" button in IDLE, etc.)
2. Importing the file as a module

The first way is the way that you most likely have been using if you have been doing the exercises in this blog. If you have many files in a large project, this is how you run the "entry point" file in the project. 

The second way is more subtle: it is what happens when you write an `import` statement at the top of your file. In this exercise for example, you need to `import random` into your program to use the random module. Somewhere on your computer there is a file (or a group of Python files) that make up the `random` module, and in the process of importing them, what you are actually doing is running the file(s) from that module. 

When you have functions defined inside a file (with the `def` keyword, like the `def square` function above) and run a file, the function is not immediately run. You can think what happens is the function is stored for future use. 

Anything else in the file - variables created, functions that are called, operations done, etc - are executed immediately when a Python file is run. 

However, in the case where you are importing a Python file into another, you want to load all of the functions without creating variables or executing any functions. You just want to load them to use them later. How do you reconcile this problem? With the `if __name__=="__main__"` statement. Create your variables and all your functions inside this statement, and when you import your file into another, it will not mess up your program by creating variables or calling functions.

What the `if __name__=="__main__"` statement from above does is ensure that variables that are created, functions that are called, operations that are done, etc ONLY when you directly run the file, not when you import it into another. 
