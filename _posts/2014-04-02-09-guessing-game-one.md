---
layout: post
number: 9
chili: 3
categories: [exercise]
---

## Exercise (and [Solution]({{ site.baseurl }}{% post_url 2014-04-10-09-guessing-game-one-solutions %}))

Generate a random number between 1 and 9 (including 1 and 9). Ask the user to guess the number, then tell them whether they guessed too low, too high, or exactly right. (_Hint: remember to use the user input lessons from the very [first exercise]({% post_url 2014-01-29-01-character-input %}_)

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

{% highlight python %}
	import random
{% endhighlight %}

This means you are allowing your Python program to use a module called `random` in the rest of your code. 

To use it (and generate a random integer), now type: 

{% highlight python %}
	a = random.randint(2, 6)
{% endhighlight %}

Once you run this program, the variable `a` will have a random integer that the computer made for you, between 2 and 6 (including 2, not including 6). 

There are many ways you can generate random numbers - integers, decimals, and much more. The [Python documentation](https://docs.python.org/3.3/library/random.html) has much more detailed information about what is possible from the `random` module.


### User input

We covered all you need to know in the [first exercise]({% post_url 2014-01-29-01-character-input %}) of this blog! 

{% include submit.md %}