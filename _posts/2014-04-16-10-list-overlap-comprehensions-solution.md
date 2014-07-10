---
layout: post
number: 10
tags: [solution]
---

## [Exercise]({{ site.baseurl }}{% post_url 2014-04-10-10-list-overlap-comprehensions %})

This week's exercise is going to be revisiting an old exercise (see [Exercise 5]({% post_url 2014-03-05-05-list-overlap %})), except require the solution in a different way. 

Take two lists, say for example these two: 

{% highlight python %}
	a = [1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]
	b = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13]
{% endhighlight %}

and write a program that returns a list that contains only the elements that are common between the lists (without duplicates). Make sure your program works on two lists of different sizes. Write this in one line of Python. (_Hint: Remember [list comprehensions]({% post_url 2014-03-19-07-list-comprehensions %}) from Exercise 7_).

Extra: 

* Randomly generate two lists to test this


## Sample solution

Great example of a solution including the extras!

<script src="https://gist.github.com/anonymous/10904252.js"></script>