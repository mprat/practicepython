## Exercise

Ask the user for a number. Depending on whether the number is even or odd, print out an appropriate message to the user. 

## Discussion

Concepts for this week: 

* Modular arithmetic (the modulus operator)
* Conditionals (if statements)
* Checking equality

### Modular arithmetic (the modulus operator)

We have been doing arithmetic (addition, subtraction, multiplication, division) since elementary school, and often it is useful for us to find not the answer to a division problem but the remainder when we do a division operation. This operation is called the "modulus operation." 

In the Python shell: 

	```
	>>> 5 % 3
	2
	>>> 6 % 3
	0
	>>> 7 % 3
	1
	```

The `%` sign is exactly the modulus operator. 

### Conditionals

A computer (or a program's) way of making a decision is through a "conditional" - whether a particular condition (statement) is true or not. You just check whether something is true, and only do the next part if the statement is in fact true.

```
if (x > 3):
	print "x is greater than 3"
elif (x < 3):
	print "x is less than 3"
else: 
	print "x is equal to 3"
```

Note that the concatenation `elif` stands for "else if". 

### Checking for equality

A fundamental thing you want to do with your program is check whether some number is equal to another. Say the user tells you how many questions they answered incorrectly on a practice exam, and depending on the number of correctly-answered questions, you can suggest a specific course of action.

Checking equality for numbers and strings is different. MORE EXPLANATION HERE