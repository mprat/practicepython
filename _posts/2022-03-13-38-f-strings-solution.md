---
layout: post
categories: [solution]
number: 38
chili: 1
title: f Strings Solution
---

## Exercise

Implement the same exercise as [Exercise 1]({% post_url 2014-01-29-01-character-input %}) (Create a program that asks the user to enter their name and their age. Print out a message addressed to them that tells them the year that they will turn 100 years old), except use f-strings instead of the `+` operator to print the resulting output message.

## Solution

In the [exercise 1 solution]({% post_url 2014-02-05-01-character-input-solutions %}), we had to convert the variable `year` into a string so that we could construct a full string and print it. Instead, here we use f-strings to directly convert the variable `year` into a string using Python internals.

{% highlight python %}
name = input("What is your name: ")
age = int(input("How old are you: "))
year = 2014 - age + 100
print(f"{name}, you will be 100 years old in the year {year}")
{% endhighlight %}
