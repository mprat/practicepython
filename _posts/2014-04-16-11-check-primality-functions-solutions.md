---
layout: post
number: 11
categories: [solution]
---

Ask the user for a number and determine whether the number is prime or not. (For those who have forgotten, a prime number is a number that has no divisors.). You can (and should!) use your answer to [Exercise 4]({% post_url 2014-02-26-04-divisors %}) to help you. 

## Sample solution

There are many ways of solving this problem, so here are a sample solutions:

This one is a different breakdown of functions to solve the problem. The strings between three `'''` marks are comments in the code that describe what each function does.

<script src="https://gist.github.com/JamieMacIver/11196563.js"></script>

And here is a solution without using functions. It is also a correct solution that accomplishes the given task, just without the use of functions. 

<script src="https://gist.github.com/evamvid/4ada99be543f08280fb0.js"></script>

This solution doesn't use functions, but does use list comprehensions, which are always fun. Thanks to Carlos for this solution. The interesting thing here is the observation that when you want to check if a number is prime, all you need to do is check the numbers from 2 to the square root of the number. This is because the pair of numbers that are both the largest factors of the number are `square root of x` and `square root of x`. Otherwise, the number you are checking for can be found by finding the corresponding factor and checking it. 

<script src="https://gist.github.com/cescapa/c655e8e0c1558660150f.js"></script>

Another solution is a clean, short solution that uses list comprehensions. 

<script src="https://gist.github.com/anonymous/34620e5c9feeec8824df.js"></script>

