---
layout: post
number: 35
chili: 2
part: 3
of: 4
part_text: birthday data
categories: [exercise]
---

{% include exercise_header.md number=page.number %}

{% include parts_sentence.md part=page.part part_text=page.part_text part_of=page.of %} 

In the [previous exercise]{{ site.baseurl }}{% post_url 2017-02-06-34-birthday-json %} we saved information about famous scientists' names and birthdays to disk. In this exercise, load the JSON file from disk, extract the months of all the birthdays, and count how many scientists have a birthday in each month.

Your program should output something like:

{% highlight python %}
{
	"May": 3,
	"November": 2,
	"December": 1
}
{% endhighlight %}

## Discussion

You already have the skills to achieve this exercise with concepts we've already covered: for loops, dictionaries, and basic arithmetic. However, I want to talk about a Python built-in called a `Counter`.

A [`Counter`](https://docs.python.org/3/library/collections.html#collections.Counter) takes a list and counts how many of each element were in the list. To use the Counter, first import it from `collections`:

{% highlight python %}
from collections import Counter
{% endhighlight %}

This lets you use the `Counter` data structure built into Python in your program. Then, give it a list: 

{% highlight python %}
my_list = [1, 6, 5, 1, 6, 5, 1]
c = Counter(my_list)
{% endhighlight %}

