---
layout: post
number: 20
categories: [solution]
published: True
---

Write a function that takes an ordered list of numbers (a list where the elements are in order from smallest to largest) and another number. The function decides whether or not the given number is inside the list and returns (then prints) an appropriate boolean.

Extras: 

* Use binary search. 

## Sample solution 

There are two ways of solving this problem: one version using a simple for loop to search through the elements of a list, and one using the concept of binary search, looking at the elements in the most efficient way possible. 

To use a simple for loop, a program will look like this: 

{% gist mprat/074b2a4b9411a6e04c25 element-search.py %}

And to use binary search, one way of writing this program is like this:

{% gist mprat/074b2a4b9411a6e04c25 element-search-binary-search.py %}

Note that there are many ways of implementing binary search correctly. One common technique is to use what is called "recursion" or "dynamic programming", which calls a function from inside the function. What I have shown here is an example of binary search written with just the concepts of a `while` loop and `if` statements that we have seen before in this blog.