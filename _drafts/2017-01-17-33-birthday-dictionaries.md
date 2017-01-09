---
layout: post
number: 33
chili: 1
categories: [exercise]
---

## Exercise

_This exercise is Part 1 of 4 of the Birthday data exercise series. The other exercises are: [Part 2]({{ site.baseurl }}/exercise/comingsoon), [Part 3]({{ site.baseurl }}/exercise/comingsoon), and [Part 4]({{ site.baseurl }}/exercise/comingsoon)._

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

## Discussion topics

1. Dictionaries
2. String formatting, briefly

### Dictionaries

The main topic for this week is the concept of a *dictionary*. In Python they are called dictionaries, but in other languages they may be called _maps_ or _hashmaps_. The concept is the same: it is a way to use a _key_ to access some _value_. It is mapping one set of data (the keys) to another set of data (the values). The only way to access the _value_ part of the dictionary is to use the _key_.

As an example, grocery store systems can store the prices for various items by using a dictionary. In Python, it would look something like this:

{% highlight python %}
price_dictionary = {
	"banana": 1.50,
	"avocado": 0.99,
	"heirloom tomato": 0.89,
	"cherry tomato pack": 3.00
}
{% endhighlight %}

You specify the dictionary with the `{}`. Key / value pairs are specified as list (separated by commas) 

### String formatting
