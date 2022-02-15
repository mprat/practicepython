---
layout: post
number: 4
categories: [solution]
---

Create a program that asks the user for a number and then prints out a list of all the divisors of that number. (If you don't know what a _divisor_ is, it is a number that divides evenly into another number. For example, 13 is a divisor of 26 because 26 / 13 has no remainder.)

## Sample solution

<script src="https://gist.github.com/jeffhunt/9269773.js"></script>

There were a number of tricky things with this exercise. First, the type conversions between input strings and integers for the `range()` function need to be carefully output. Second, the arguments to `range()` had to be carefully constructed to cover all the possible numbers. Third, the condition in the `if` statement had to be correct as well. 