---
layout: post
number: 5
chili: 2
categories: [exercise]
---

## Exercise (and [Solution]({{ site.baseurl }}{% post_url 2014-03-19-05-list-overlap-solutions %}))

Take two lists, say for example these two: 

{% highlight python %}
  a = [1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]
  b = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13]
{% endhighlight %}

and write a program that returns a list that contains only the elements that are common between the lists (without duplicates). Make sure your program works on two lists of different sizes.

Extras: 

1. Randomly generate two lists to test this
2. Write this in one line of Python (don't worry if you can't figure this out at this point - we'll get to it soon)

## List properties

In other words, "things you can do with lists."

One of the interesting things you can do with lists in Python is figure out whether something is inside the list or not. For example: 

{% highlight pycon %}
  >>> a = [5, 10, 15, 20]
  >>> 10 in a
  True
  >>> 3 in a
  False
{% endhighlight %}

You can of course use this in loops, conditionals, and any other programming constructs. 

{% highlight python %}
  list_of_students = ["Michele", "Sara", "Cassie"]

  name = input("Type name to check: ")
  if name in list_of_students:
    print("This student is enrolled.")
{% endhighlight %}

{% include submit.md %}