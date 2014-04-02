---
layout: post
title: Exercise 9
tags: [exercise]
---

## Exercise

Generate a random number between 1 and 9 (including 1 and 9). Ask the user to guess the number, then tell them whether they guessed too low, too high, or exactly right. (_Hint: remember to use the user input lessons from the very [first exercise](http://practicepython.blogspot.com/2014/01/exercise-1-input-and-strings.html!_)

Extras: 

* Keep the game going until the user types "exit"
* Keep track of how many guesses the user has taken, and when the game ends, print this out.

## Discussion

Concepts for this week:

* Modules
* Random numbers
* User input

### Random Numbers (and Modules)

This is your first exposure to using Python code that somebody else wrote. In Python, these formally-distributed code packages are called *modules*. The thing we want from a module in this exercise is the ability to generate random numbers. This comes from the *random* module. 

To use a module, at the top of your file, type 

```
import random
```

This means you are allowing your Python program to use a module called `random` in the rest of your code. 

To use it (and generate a random integer), now type: 

```
a = random.randint(2, 6)
```

Once you run this program, the variable `a` will have a random integer that the computer made for you, between 2 and 6 (including 2, not including 6). 

There are many ways you can generate random numbers - integers, decimals, and much more. The [Python documentation](https://docs.python.org/3.3/library/random.html) has much more detailed information about what is possible from the `random` module.


### User input

We covered all you need to know in the [first exercise](http://practicepython.blogspot.com/2014/01/exercise-1-input-and-strings.html) of this blog! 

## Happy Coding!
Forgot how to [submit exercises](http://practicepython.blogspot.com/2014/01/how-it-works.html)?

<iframe src="https://docs.google.com/forms/d/1WukNfdIjINTKLJRIcKJ6pmMbfd9A3PXqhOVpWRhlRF4/viewform?embedded=true" width="300" height="300" frameborder="0" marginheight="0" marginwidth="0">Loading...</iframe>