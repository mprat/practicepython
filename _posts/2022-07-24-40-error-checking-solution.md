---
layout: post
categories: [solution]
number: 40
chili: 3
published: true
---

## Exercise

Given this solution to [Exercise 9]({% post_url 2014-04-02-09-guessing-game-one%}), modify it to have one level of user feedback: if the user does not enter a number between 1 and 9, tell them. Don't count this guess against the user when counting the number of guesses they used.

{% highlight python %}
import random

number = random.randint(1, 9)
number_of_guesses = 0
while True:
	guess = int(input("Guess a number between 1 and 9: "))
	number_of_guesses += 1
	if guess == number:
		break
print(f"You needed {number_of_guesses} guesses to guess the number {number}")
{% endhighlight %}

## Solution

Using the terminology from the discussion in the [exercise]({% post_url 2022-07-17-40-error-checking %}), the exercise is asking to implement one logical error handling (i.e. making sure the guess is between the numbers 1 and 9) and one Pythonic error handling (making sure the input is strictly a number).

So the solution combines the two techniques discussed.

Firstly, we need to implement an "inner loop" to make sure we have a loop set up to ask the user over and over again for a guess. This is the default - we always ask the user, and only "break" out of the loop when the user's input meets all of our criteria. The logical error check is implemented with an `if` statement: if the guess is between the numbers 1 and 9, we break out of the inner loop. The Pythonic error check is implemented using a `try` / `catch` statement. Combining these two cases is subtle: we put the logical check inside the `try` clause of the Pythonic check - this is `if` statement will then only get executed if the previous line (the line with the `int(input())`) does not throw a `ValueError`. This is a very "Pythonic" way of implemeting the solution to this problem - rather than having two separate checks one after the other, we take advantage of the properties of `try` / `catch` blocks to do both for us!

Check it out:

{% highlight python %}
import random

number = random.randint(1, 9)
number_of_guesses = 0
while True:
	while True:
		try:
			guess = int(input("Guess a number between 1 and 9: "))
			if guess >= 1 and guess <= 9:
				break
			else:
				print("Your input must be a number between 1 and 9 inclusive")
		except ValueError:
			print("You must enter a number")
	number_of_guesses += 1
	if guess == number:
		break
print(f"You needed {number_of_guesses} guesses to guess the number {number}")
{% endhighlight %}