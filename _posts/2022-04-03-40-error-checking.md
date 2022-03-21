---
layout: post
categories: [exercise]
number: 40
published: false
chili: 3
---

## Exercise

Given this solution to [Exercise 9]({% post_url 2014-04-02-09-guessing-game-one%}), modify it to have one level of user feedback: if the user does not enter a number between 1 and 9, tell them. Don't count this guess against the user when counting the number of guesses they used.

```
import random

number = random.randint(1, 9)
number_of_guesses = 0
while True:
	guess = int(input("Guess a number between 1 and 9: "))
	number_of_guesses += 1
	if guess == number:
		break
print(f"You needed {number_of_guesses} guesses to guess the number {number}")
```


## Discussion

### An Example

When writing a program that will interact with a person, it is always important to remember that people are not machines. They will accidentally input incorrect data, or will mis-understand instructions given when entering inputs. As programmers, we don't want any incorrect data to cause our programs to crash.

Let's first take a the small program from the exercise above (without any error checks) and see what kind of error can happen. If we run the program above, except enter the string "`testing`" instead of a number, here is the output error we see:

{% highlight python %}
Guess a number between 1 and 9: testing
---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
<ipython-input-1-20913a3822f0> in <module>
      4 number_of_guesses = 0
      5 while True:
----> 6         guess = int(input("Guess a number between 1 and 9: "))
      7         number_of_guesses += 1
      8         if guess == number:

ValueError: invalid literal for int() with base 10: 'testing'
{% endhighlight %}

The line `ValueError: invalid literal for int() with base 10: 'testing'` is telling us that there is an error with the value being input into the `int()` function. Namely, the string "`testing`" can't be converted into an `int()`. This makes sense - it's not an `int`! This isn't a logical error, it's an error with a data type.

There are many kinds of errors that can happen. Another example of an error is a "logical error" where a user doesn't follow the instructions given. This doesn't cause a crash in the program, but leads to a slightly misleading user experience:

{% highlight python %}
>>> Guess a number between 1 and 9: 100
>>> Guess a number between 1 and 9: 1
>>> Guess a number between 1 and 9: 2
>>> Guess a number between 1 and 9: 3
You needed 4 guesses to guess the number 3
{% endhighlight %}

Notice how the program lets the user enter the number 100, despite asking for a number between 1 and 9. The number of guesses is counted as 4, although one would argue that the guess 100 was an "invalid guess" and therefore shouldn't have been counted as a guess. Since there is no way 100 would be the correct answer, might as well not penalize the incorrect guess.

This type of error doesn't crash our program, but leads to a bad user experience.

The handling of data type / programming errors and logical errors needs a different treatment, which we'll address in the next two sections.

### Pythonic error handling

Different programming languages handle programming errors differently. In Python, the mantra is "ask forgiveness, not permission". What I mean is that we "let" the program execute and throw and error, but "catch" it and do something about it later. This is a bit of an unusual paradigm - wouldn't it make more sense to NEVER have the program throw an error in the first place? Sure, that can be done as well. In Python however, throwing an error isn't a big deal, as long as we catch it. It also makes the code clear to understand which error we CAN handle and which we CANNOT. In Python, when the program throws an error, that error is called an `Exception`.

The mechanism to "catch" an error in the program is called a `try` / `catch` block. The official Python documentation has a section about [handing exceptions](https://docs.python.org/3/tutorial/errors.html#handling-exceptions) that goes into detail about what exceptions are and how to extend them, for more detailed reading.

The way to think about a `try` / `catch` block is that the "try" section is asking the program to execute something, and the "catch" block is executed if the code in the "try" section throws an exception. When we write a "catch" block, we always should specify what kind of exception we want to catch. In the example above, when the string `testing` was entered instead of a number, the `int()` code throws a `ValueError` exception. So if we want to catch that error, we specify it specifically:

{% highlight python %}
try:
	guess = int(input("Guess a number between 1 and 9: "))
	print(f"You entered {guess}")
except ValueError:
	print("ValueError as thrown")
{% endhighlight %}

And we see the following:

{% highlight python %}
>>> Guess a number between 1 and 9: 8
You entered 8
{% endhighlight %}

{% highlight python %}
>>> Guess a number between 1 and 9: testing
ValueError as thrown
{% endhighlight %}

Notice how the program didn't crash spectacularly in the second case - it simply kept going! In the first case (when everything was OK with the input) the code in the "catch" block did not execute, and we didn't need it to.

Adding a `try`/`catch` block to the code in the exercise will require some playing around with loops, but it can be done! Check out the [solution](% post_url 2022-04-10-40-error-checking-solution %) to see how.

### Logical error handling

The `try`/`catch` paradigm detailed in the section above doesn't work for logical program errors. Why? Because in that case, there is no exception thrown! In the example of a user entering 100 when asked for a number between 1 and 9, the program continues on it's way, so there's nothing to catch.

In the case of checking for logical errors, we need to be a bit more clever when writing our programs. Namely, we need to write more code! In the case of the example program above, if we truly don't want to allow guesses that are not between 1 and 9, we need to check for that case:

{% highlight python %}
guess = int(input("Guess a number between 1 and 9: "))
if guess < 1 or guess > 9:
	print("Guess again!")
{% endhighlight %}

In this snippet, we use an `if` statement to check whether the user input guess satisfies our standards. Of course, to finish this exercise, we need to account for not counting the number of guesses in this case, and make sure we ask the user to enter a new number. Check out the [solution](% post_url 2022-04-10-40-error-checking-solution %) to see how.
