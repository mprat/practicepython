---
layout: post
number: 28
chili: 1
categories: [solution]
---

{% include solution_header.md number=page.number %}

Implement a function that takes as input three variables, and returns the largest of the three. Do this without using the Python `max()` function!

## Sample solutions

There are many ways to answer this question, ranging from simple to complex. Here are a few reader-submitted answers!

This first example solution uses a series of `if` statements and comparisons to find the largest of 3 elements.

<script src="https://gist.github.com/zhangyu1534/74c42eee472f929034ff373ec91b9c1c.js"></script>

Another solution is a little bit less verbose, taking 3 numbers as an input, making them into a list, sorting them, and then reading off the largest element.

<script src="https://gist.github.com/kuko-mainroot/d9a1109ef138c93f73a01661178b820a.js"></script>

This last solution uses a more compact series of `if` statement comparisons to cover all cases of 3 elements.

<script src="https://gist.github.com/kanampalli/f35bc42895fad02336b780acd60044ec.js"></script>

Which one is your favorite? Why?

Happy hacking!