Calibrating the exercises to the audience is going to be a challenging task, so I ask you to bear with me if the exercises are too easy or too hard. Every week there will be a poll you can click on to vote whether the exercise is too easy or too hard, and hopefully after a few weeks I will get the level right. I will start with the exercise and include a discussion after, in case you want the extra challenge. The exercise will also be followed by a few "bonus" tasks if you want to fill up your half an hour of coding time, or if you want to take some extra time to code this week.

## Exercise

Take a list, say for example this one: 

```
a = [1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]
```

and write a program that prints out all the elements of the list that are less than 5.

Extras: 

1. Instead of printing the elements one by one, make a new list that has all the elements less than 5 from this list in it and print out this new list.
2. Write this in one line of Python.
3. Ask the user for a number and return a list that contains only elements from the original list `a` that are smaller than that number given by the user. 

## Discussion 

This week's topics:
1. Lists
2. More conditionals (if statements)

### Lists

This week's exercise hits on a topic critical for all types and styles of programming: **lists**. Lists are basically an ordered way of grouping things (called **elements**) - the cool thing about lists in Python is that you can have a list that contains objects of multiple types. Your list can mix between strings, integers, objects, other lists, what have you. 

The way to construct an empty list is just to do 

```
x = []
```

And your variable `x` now holds an empty list. To add things to this list, just "append" them to the list. Like so: 

```
x = []
x.append(3)
```

Your list `x` now looks like `[3]`.

In Python, lists are also **iterables**, which means you can loop through them with a **for loop** in a convenient way. (If you come from other languages like C++ or Java you are most likely used to using a counter to loop through indices of a list - in Python you can actually loop through the elements.) I will let the code speak for itself: 

```
my_list = [1, 3, "Michele", [5, 6, 7]]
for element in my_list:
	print element
```

Will yield the result: 
```
1 
3
"Michele"
[5, 6, 7]
```

There are many other properties of lists, but for the basic exercise all you should need is this for loop property. 

For more information about lists in Python, check out these resources: 

* [The official Python documentation on lists](http://docs.python.org/3.3/tutorial/datastructures.html)
* [Tutorialspoint on Python lists](http://www.tutorialspoint.com/python/python_lists.htm)
* [Someone else's blog post about lists](http://effbot.org/zone/python-list.htm)


### More Conditionals

The nice thing about conditionals is that they follow logical operations. 