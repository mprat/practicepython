---
layout: post
categories: [solution]
number: 39
published: true
---

## Exercise

Implement the same exercise as [Exercise 1]({% post_url 2014-01-29-01-character-input %}) (Create a program that asks the user to enter their name and their age. Print out a message addressed to them that tells them the year that they will turn 100 years old), except don't explicitly write out the year. Use the built-in Python `datetime` library to make the code you write work during every year, not just the one we are currently in.

## Solution

To figure out the year in which someone will turn 100, we need to take the current year, subtract their current age, and add 100. We use the `datetime` library to get the current year, the `input()` function (see [exercise 1]({% post_url 2014-01-29-01-character-input %})) to ask the user their name and age, and f-strings (see [exercise 38]({% post_url 2022-03-06-38-f-strings %})) to print out the result.

{% highlight python %}
import datetime

current_year = datetime.datetime.now().year
name = input("What is your name? ")
age = int(input("How old are you? "))
print(f"{name}, you will be 100 years old in {current_year - age + 100}")
{% endhighlight %}

Take a look at the difference between this solution and the hard-coded one in [exercise 1]({% post_url 2014-02-05-01-character-input-solutions %}), where the year does not update automatically.
