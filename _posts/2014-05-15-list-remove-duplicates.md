---
layout: post
number: 14
tags: [exercise]
---

## Exercise

Write a program (function!) that takes a list and returns a new list that contains all the elements of the first list minus all the duplicates. 

Extras: 

* Write two different functions to do this - one using a loop and constructing a list, and another using sets.
* Go back and do [Exercise 5](http://practicepython.blogspot.com/2014/03/exercise-5-list-overlap.html) using sets, and write the solution for that in a different function.

## Discussion

Concepts for this week:

* Sets

### Sets

In mathematics, a **set** is a collection of elements where no element is repeated. This becomes useful because if you know your data is stored in a set, you are guaranteed to have unique elements. 

## Features of sets

* Sets are **not ordered**. This means that there is no "first element" or "last element." There are just "elements". You cannot ask a set for it's "next element".
* There are no repeat elements in sets.
* You can convert between sets and lists very easily. 

## In Python 

In Python, you make and use a set with the `set()` keyword. For example: 

```
names = set()
names.add("Michele")
names.add("Robin")
names.add("Michele")
print(names)
```

And the output will be; 

```
set(['Michele', 'Robin'])
```

You can do to a set almost anything you can do to a list (except ask for things like "the third element"). See the [Python documentation about sets](https://docs.python.org/3.3/library/stdtypes.html?highlight=set#set) to get a full list of things you can do to sets. 

You can convert from a list to a set and a set to a list pretty easily: 

```
names = ["Michele", "Robin", "Sara", "Michele"]
names = set(names)
names = list(names)
print(names)
```

And the result of this will be: 

```
['Michele', 'Robin', 'Sara']
```

Explore away!
 
## Happy coding! 

Forgot how to [submit exercises](http://practicepython.blogspot.com/2014/01/how-it-works.html)?

<iframe src="https://docs.google.com/forms/d/1WukNfdIjINTKLJRIcKJ6pmMbfd9A3PXqhOVpWRhlRF4/viewform?embedded=true" width="300" height="300" frameborder="0" marginheight="0" marginwidth="0">Loading...</iframe>