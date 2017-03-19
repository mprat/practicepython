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

## Reader solution

Here is one reader solution using built-in Counters. This reader's solution did not specify what kind of format the months have to be in, but as you can see from their use of `x.split()[0]` to extract the months that they expect the month format to be of the type "May 5, 2010".

<script src="https://gist.github.com/esclavosoy/19829e8486f88da3ab42b1fedc3f6936.js"></script>

## My solution

In the [previous exercise]({{ site.baseurl }}{% post_url 2017-02-06-34-birthday-json %}), I saved birthday information in a slightly different format, so I had to use a slightly different method to extract the months. In my dictionary, the birthdays were saved in the format "MM/DD/YYYY", or the standard date format we use in the US. My `birthdays.json` file looked like this:

{% highlight python %}
{
	"Albert Einstein": "03/14/1879",
	"Ada Byron Lovelace": "12/10/1815",
	"Benjamin Franklin": "01/17/1706"
}
{% endhighlight %}

To count how many birthdays are in each month, what we need to do is:

1. Extract the number that represents the month
2. Convert that number to a string
3. Print the result

Here is my code to do that:

{% highlight python %}
import json
from collections import Counter

with open("info.json", "r") as f:
	birthdays = json.load(f)

num_to_string = {
	1: "January",
	2: "February",
	3: "March", 
	4: "April",
	5: "May",
	6: "June",
	7: "July",
	8: "August",
	9: "September",
	10: "October",
	11: "November",
	12: "December"
}

months = []
for name, birthday_string in birthdays.items():
	month = int(birthday_string.split("/")[0])
	months.append(num_to_string[month])

print(Counter(months))
{% endhighlight %}

And the output you will see is:

{% highlight python %}
Counter({'January': 1, 'March': 1, 'December': 1})
{% endhighlight %}

Happy coding!