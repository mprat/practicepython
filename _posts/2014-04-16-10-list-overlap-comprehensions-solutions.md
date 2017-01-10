---
layout: post
number: 10
categories: [solution]
---

## [Exercise {{ page.number }}]({{ site.baseurl }}{% post_url 2014-04-10-10-list-overlap-comprehensions %})

This week's exercise is going to be revisiting an old exercise (see [Exercise 5]({% post_url 2014-03-05-05-list-overlap %})), except require the solution in a different way. 

Take two lists, say for example these two: 

{% highlight python %}
	a = [1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]
	b = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13]
{% endhighlight %}

and write a program that returns a list that contains only the elements that are common between the lists (without duplicates). Make sure your program works on two lists of different sizes. Write this *using at least one list comprehension*. (_Hint: Remember [list comprehensions]({% post_url 2014-03-19-07-list-comprehensions %}) from Exercise 7_).

Extra: 

* Randomly generate two lists to test this


## Sample solution

A user-submitted solution:

<script src="https://gist.github.com/anonymous/10904252.js"></script>

As a few commenters / readers of this blog have pointed out (thanks mainly to Gautam and Jeff), the exercise as posed is actually impossible to write in a single line of Python. The problem is this: the proposed reader solution (and the solution that I had in mind myself) as written above does not take into account the fact that there might be duplicates in the resulting list, where I specifically asked to not include duplicates. This means that in the simple example I gave above, `a`'s first element is `1` will be added to the `result` list because it is in `b`. But then it's next element is also `1`, and is also in `b`, so will be added to the `result` list. So the solution as given (the comprehension `[i for i in a if i in b]`) will not yield the correct result on the example solution. 

Instead, as pointed out by Gautam and Jeff, the simplest way to achieve this solution would be to make sure that we are only looking at unique elements from `a`, the first list in the comprehension. We have not discussed doing this easily in Python on this blog using the `set` built-in function, but if you know it, the solution will look like this:

{% gist mprat/654b5f9286bcc2469077 list-overlap-comprehensions.py %}

But, to achieve the same results as asked in the original question while still using a list comprehension (however, definitely not using a single line of code), would be to make sure that there is no overlap in the new list after it is constructed, using the traditional `for` loop on lists:

{% gist mprat/654b5f9286bcc2469077 list-overlap-comprehensions-for.py %}

Or, to practice list comprehensions again, this can be done with two list comprehensions:

{% gist mprat/654b5f9286bcc2469077 list-overlap-comprehensions-2.py %}