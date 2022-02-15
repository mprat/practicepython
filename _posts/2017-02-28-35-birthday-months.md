---
layout: post
number: 35
chili: 2
part: 3
of: 4
part_text: birthday data
categories: [exercise]
---

In the [previous exercise]({{ site.baseurl }}{% post_url 2017-02-06-34-birthday-json %}) we saved information about famous scientists' names and birthdays to disk. In this exercise, load that JSON file from disk, extract the months of all the birthdays, and count how many scientists have a birthday in each month.

Your program should output something like:

{% highlight python %}
{
	"May": 3,
	"November": 2,
	"December": 1
}
{% endhighlight %}

## Discussion

You already have the skills to achieve this exercise with concepts we've already covered: [for loops]({{ site.baseurl }}{% post_url 2014-02-15-03-list-less-than-ten %}), [dictionaries]({{ site.baseurl }}{% post_url 2014-12-06-22-read-from-file %}), and basic arithmetic. However, I want to talk about a Python built-in called a `Counter`.

A [`Counter`](https://docs.python.org/3/library/collections.html#collections.Counter) takes a list and counts how many of each element were in the list. To use the Counter, first import it from `collections`:

{% highlight python %}
from collections import Counter
{% endhighlight %}

This lets you use the `Counter` data structure built into Python in your program. Then, give it a list: 

{% highlight python %}
sandwiches = ["ham", "cheese", "roast beef", "ham", "cheese", "roast beef", "ham"]
c = Counter(sandwiches)
{% endhighlight %}

If you `print(c)`, you will see this:

{% highlight python %}
Counter({"ham": 3, "roast beef": 2, "cheese": 2})
{% endhighlight %}

This means there are 3 `ham`, 2 `roast beef`, and 2 `cheese` sandwiches in my list. I can get this information directly from the `Counter`:

{% highlight python %}
>>> print("There are {} ham sandwiches".format(c["ham"]))
There are 3 ham sandwiches
{% endhighlight %}

Hope this is useful!
