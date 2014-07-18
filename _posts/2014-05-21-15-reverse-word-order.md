---
layout: post
number: 15
categories: [exercise]
---

## Exercise (and [Solution]({{ site.baseurl }}{% post_url 2014-05-28-15-reverse-word-order-solutions %}))

Write a program (using functions!) that asks the user for a long string containing multiple words. Print back to the user the same string, except with the words in backwards order. For example, say I type the string: 

{% highlight python %}
  My name is Michele
{% endhighlight %}

Then I would see the string: 

{% highlight python %}
  Michele is name My
{% endhighlight %}

shown back to me.

## Discussion

Concepts for this week:

* More string things

## More string things 

Python has a lot of interesting things you can do with strings. I will show a few here, but you can see many more methods that may or may not be useful at the [official Python documentation about the string format](https://docs.python.org/3.3/library/stdtypes.html?highlight=strings#string-methods).

Remember that [strings are lists]({% post_url 2014-03-12-06-string-lists %}).

### Splitting strings

You can "split" or tear apart strings based on a given set of characters. For example: 

{% highlight python %}
  teststring = "this is a test"
  result = teststring.split("t")
{% endhighlight %}

And at the end, `result` will contain the list:

{% highlight python %}
  ['', 'his is a ', 'es', '']
{% endhighlight %}

Instead of `"t"`, you can write any character you want. If you do not include any character, it means "split on all whitespace": 

{% highlight python %}
  teststring = "  this      has a lot    of   spaces and    tabs"
  result = testring.split()
{% endhighlight %}

Then `result` contains: 

{% highlight python %}
  ['this', 'has', 'a', 'lot', 'of', 'spaces', 'and', 'tabs']
{% endhighlight %}

### Joining strings

You can also relatively easily "join" or "smush" strings together: 

{% highlight python %}
  listofstrings = "['a', 'b', 'c']"
  result = "**".join(listofstrings)
{% endhighlight %}

Then `result` will contain the string: 

{% highlight pycon %}
  a**b**c
{% endhighlight %}

Take a look at the official Python documentation for more information.
 
{% include submit.md %}