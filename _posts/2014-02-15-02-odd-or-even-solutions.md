---
layout: post
number: 2
categories: [solution]
---

{% include solution_header.md number=page.number %}

Ask the user for a number. Depending on whether the number is even or odd, print out an appropriate message to the user. 

_Hint: how does an even / odd number react differently when divided by 2?_

Extras: 

1. If the number is a multiple of 4, print out a different message. 
2. Ask the user for two numbers: one number to check (call it `num`) and one number to divide by (`check`). If `check` divides evenly into `num`, tell that to the user. If not, print a different appropriate message.

## Sample solution

There are many ways of doing the exercise, so I am posting a few sample solutions. The very basics: 

<script src="https://gist.github.com/anonymous/8838738.js"></script>

And something that looks slightly more complex (but is just a more complicated conditional): 

<script src="https://gist.github.com/eugenepark81/1fd606c626c1946ddcc8.js"></script>