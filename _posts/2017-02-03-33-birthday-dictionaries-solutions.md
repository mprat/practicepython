---
layout: post
number: 33
chili: 1
part: 1
of: 4
part_text: birthday data
categories: [solution]
---

{% include solution_header.md number=post.number %}

{% include parts_sentence.md part=page.part part_text=page.part_text part_of=page.of %}

For this exercise, we will keep track of when our friend's birthdays are, and be able to find that information based on their name. Create a dictionary (in your file) of names and birthdays. When you run your program it should ask the user to enter a name, and return the birthday of that person back to them. The interaction should look something like this:

{% highlight pycon %}
>>> Welcome to the birthday dictionary. We know the birthdays of:
Albert Einstein
Benjamin Franklin
Ada Lovelace
>>> Who's birthday do you want to look up?
Benjamin Franklin
>>> Benjamin Franklin's birthday is 01/17/1706.
{% endhighlight %}

## Sample solution

One reader does the basics:

<script src="https://gist.github.com/Dimithrandir/75b943f35297a0708a9393d02dfe2121.js"></script>

And here is another reader submission:

<script src="https://gist.github.com/nhyy24/5efa95d627902eba38dbfd1e6f853340.js"></script>

