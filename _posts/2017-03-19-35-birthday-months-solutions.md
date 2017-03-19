---
layout: post
number: 35
chili: 2
part: 3
of: 4
part_text: birthday data
categories: [solution]
---

{% include solution_header.md number=page.number %}

{% include parts_sentence.md part=page.part part_text=page.part_text part_of=page.of %}

In the [previous exercise]({{ site.baseurl }}{% post_url 2017-02-06-34-birthday-json %}) we saved information about famous scientists' names and birthdays to disk. In this exercise, load that JSON file from disk, extract the months of all the birthdays, and count how many scientists have a birthday in each month.

Your program should output something like:

{% highlight python %}
{
	"May": 3,
	"November": 2,
	"December": 1
}
{% endhighlight %}

## Sample solution

Here is one reader solution using built-in Counters:

<script src="https://gist.github.com/esclavosoy/19829e8486f88da3ab42b1fedc3f6936.js"></script>

Happy coding!