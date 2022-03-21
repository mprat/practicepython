---
layout: post
categories: [exercise]
number: 40
published: false
chili: 3
---

## Exercise

Given this solution to Exercise 9, modify it to one level of user feedback: if the user does not enter a number between 1 and 9, tell them. Don't count this guess against the user when counting the number of guesses they used.

```
import random

number = random.randint(1, 9)
number_of_guesses = 0
while True:
	guess = int(input("Guess a number between 1 and 9: "))
	number_of_guesses += 1
	if guess == number:
		break
print(f"You needed {number_of_guesses} to guess the number {number}")
```


## Discussion

error checking on inputs
can use exercise8 as an example to walk through, since there are a lot of potential error checks
