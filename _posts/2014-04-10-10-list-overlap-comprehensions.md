---
layout: post
number: 10
tags: [exercise]
---

## Exercise

This week's exercise is going to be revisiting an old exercise (see [Exercise 5](http://practicepython.blogspot.com/2014/03/exercise-5-list-overlap.html)), except require the solution in a different way. 

Take two lists, say for example these two: 

```
a = [1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]
b = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13]
```

and write a program that returns a list that contains only the elements that are common between the lists (without duplicates). Make sure your program works on two lists of different sizes. Write this in one line of Python. (_Hint: Remember [list comprehensions](http://practicepython.blogspot.com/2014/03/exercise-7-list-comprehensions.html) from Exercise 7_).

Extra: 

* Randomly generate two lists to test this

## Discussion

Concepts for this week:

* List comprehensions
* Random numbers, continued

### List comprehensions

We already discussed list comprehensions in [Exercise 7](http://practicepython.blogspot.com/2014/03/exercise-7-list-comprehensions.html), but they can be made much more complicated. 

For example: 

```
x = [1, 2, 3]
y = [5, 10, 15]
allproducts = [a*b for a in x for b in y]
```

At the end of this piece of code, `allproducts` will contain the list `[5, 10, 15, 10, 20, 30, 15, 30, 45]`. So you can put multiple for loops inside the comprehension. But you can also add more complicated conditionals:

```
x = [1, 2, 3]
y = [5, 10, 15]
customlist = [a*b for a in x for b in y if a*b%2 != 0]
```

Now `customlist` contains `[5, 15, 15, 45]` because only the odd products are added to the list. 

In general, the list comprehension takes the form: 

```
[EXPRESSION FOR_LOOPS CONDITIONALS]
```

as shown in the examples above.

### Random numbers, continued

Try to use the [Python random documentation](https://docs.python.org/3.0/library/random.html) to figure out how to generate a random list. As a hint look below:

```
a = random.sample(range(100), 5)
```

This line of code will leave `a` containing a list of 5 random numbers from 0 to 99. 

## Happy coding! 

Forgot how to [submit exercises](http://practicepython.blogspot.com/2014/01/how-it-works.html)?

<iframe src="https://docs.google.com/forms/d/1WukNfdIjINTKLJRIcKJ6pmMbfd9A3PXqhOVpWRhlRF4/viewform?embedded=true" width="300" height="300" frameborder="0" marginheight="0" marginwidth="0">Loading...</iframe>