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

We covered dictionaries in [a previous exercise]({{ site.baseurl }}{% post_url 2014-12-06-22-read-from-file %}), but it's been long enough that we will review them here and add a few more notes.

#### Quick review

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

You specify the dictionary between the `{}`. Key / value pairs are specified as list (separated by commas). The _key_ is on the left side, and the _value_ is on the right side. Notice how I split up the dictionary definition on multiple lines - I did that just for convenience. You can also write the dictionary on the entire line, but it is hard to read (and it probably even goes off your browser window screen):

{% highlight python %}
price_dictionary = {
	"banana": 1.50, "avocado": 0.99, "heirloom tomato": 0.89, "cherry tomato pack": 3.00}
{% endhighlight %}

Now that we have the dictionary, we can query it (ask it) for the values associated with each key (for the prices associated with each food). We do that using brackets (`[]`). For example, to get the price of a banana:

{% highlight python %}
>>> print(price_dictionary["banana"])
1.50
{% endhighlight %}

To get a list of all the keys, use the `.keys()` method:

{% highlight python %}
>>> print(price_dictionary.keys())
["banana", "avocado", "heirloom tomato", "cherry tomato pack"]
{% endhighlight %}

We have created our dictionary with many items in it, but we can also add items to it one by one. It is almost like accessing an element in the dictionary, except instead of using the element, we assign something to it.

{% highlight python %}
>>> price_dictionary["granny smith apple"] = 0.49
>>> price_dictionary["red delicious apple"] = 0.35
>>> print(price_dictionary["granny smith apple"])
0.49
{% endhighlight %}

Not all key / value pairs have to be the same. You can do something like:

{% highlight python %}
>>> price_dictionary["dog food"] = "only at Petco"
>>> print(price_dictionary["dog food"])
only at Petco
{% endhighlight %}

Of course, this can get messy quickly, so be careful!


#### More on dictionary keys

Dictionary keys must be unique. If you try to add an element to your dictionary with the same key, it will overwrite the value previously at that key:

{% highlight python %}
>>> print(price_dictionary["dog food"])
only at Petco
>>> price_dictionary["dog food"] = 10.99
>>> print(price_dictionary["dog food"])
10.99
{% endhighlight %}

If you try to ask the dictionary for a key that doesn't exist, it will throw a `KeyError` in your console, or your program will crash:

{% highlight python %}
>>> price_dictionary["lemon"]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'lemon'
{% endhighlight %}

We will talk about how to "catch" errors in later exercises, but for now, there is another way to make sure you don't throw an error. Instead of accessing elements in a dictionary with the `[]` notation, you can instead use the `.get()` method. As the second argument to `.get()`, you write down what the _default value_ is for the dictionary: if there is no key like the one you wanted, what the dictionary should return:

{% highlight python %}
>>> print(price_dictionary.get("banana", "no food like this"))
1.50
>>> print(price_dictionary.get("lemon", "no food like this"))
no food like this
{% endhighlight %}

This can be a helpful way of avoiding causing your program to crash.

Not all Python objects can be keys to a dictionary. For something to be a key in a dictionary, it must be _immutable_. Basically, it means that you can't change that variable somewhere else. So for example, numbers and strings can be keys in a dictionary, but lists cannot. Because you can `.append()` to a list, it cannot be a key in your dictionary. Lists can be values, just not keys:

{% highlight python %}
>>> price_dictionary[[1, 2, 3]] = "new food"
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'list'
>>> price_dictionary["lettuce"] = [1.50, 3.50]
>>> print(price_dictionary["lettuce"])
[1.50, 3.50]
{% endhighlight %}

Lastly, if we want to check if a particular key is in our dictonary, it is very easy. Just use the `in` keyword:

{% highlight python %}
>>> "lemon" in price_dictionary
False
>>> "banana" in price_dictionary
True
{% endhighlight %}

These checks can be used together with `if` statements to make more complex programs.

### String formatting


* INTRODUCE THE % NOTATION IN STRING FORMATTING