---
layout: post
number: 6
categories: [exercise]
---

## Exercise

Ask the user for a string and print out whether this string is a palindrome or not. (A **palindrome** is a string that reads the same forwards and backwards.)

## Discussion

Concepts for this week: 

* List indexing
* Strings are lists

### List indexing

In Python (and most programming in general), you start counting lists from the number 0. The first element in a list is "number 0", the second is "number 1", etc. 

As a result, when you want to get single elements out of a list, you can ask a list for that number element:

{% highlight pycon %}
  >>> a = [5, 10, 15, 20, 25]
  >>> a[3]
  20
  >>> a[0]
  5
{% endhighlight %}

There is also a convenient way to get sublists between two indices: 

{% highlight pycon %}
  >>> a = [5, 10, 15, 20, 25, 30, 35, 40]
  >>> a[1:4]
  [10, 15, 20]
  >>> a[6:]
  [35, 40]
  >>> a[:-1]
  [5, 10, 15, 20, 25, 30, 35]
{% endhighlight %}

The first number is the "start index" and the last number is the "end index."

You can also include a third number in the indexing, to count how often you should read from the list: 

{% highlight pycon %}
  >>> a = [5, 10, 15, 20, 25, 30, 35, 40]
  >>> a[1:5:2]
  [10, 20]
  >>> a[0:3:-1]
  [15, 10, 5]
{% endhighlight %}

To read the whole list, just use the variable name (in the above examples, `a`), or you can also use `[:]` at the end of the variable name (in the above examples, `a[:]`). 


### Strings are lists

Because strings are lists, you can do to strings everything that you do to lists. You can iterate through them: 

{% highlight python %}
  string = "example"
  for c in string: 
    print "one letter: " + c
{% endhighlight %}

Will give the result:

{% highlight pycon %}
  one letter: e
  one letter: x
  one letter: a
  one letter: m
  one letter: p
  one letter: l
  one letter: e
{% endhighlight %}

You can take sublists: 

{% highlight pycon %}
  >>> string = "example"
  >>> s = string[0:5]
  >>> print s
  exam
{% endhighlight %}

Now `s` has the string "exam" in it. 

Moral of the story: a string is a list.

{% include submit.md %}