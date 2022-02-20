---
layout: post
categories: [exercise]
number: 39
chili: 1
---

## Exercise

Implement the same exercise as [Exercise 1]({% post_url 2014-01-29-01-character-input %}) (Create a program that asks the user to enter their name and their age. Print out a message addressed to them that tells them the year that they will turn 100 years old), except don't explicitly write out the year. Use the built-in Python `datetime` library to make the code you write work during every year, not just the one we are currently in.

## Discussion

Concepts:

* Modules
* `datetime` module

### `datetime` (and Modules)

One very common thing programs are used for is to perform operations with dates and times. How hard is it for you to count the number of days between two dates? Or count the number of seconds between two specific times? Good thing someone else wrote code that already does this for us! Python distributes these other useful pieces of code as built-in libraries or _modules_. It comes standard with any Python installation, so no additional installation is required.

The built-in library in Python used for working with dates and times is called [`datetime`](https://docs.python.org/3/library/datetime.html). The structures and functions in the library will be useful to solve the exercise.

To use a built-in library or module, we need to import this module into our current code. (For another use case for modules, see [Exercise 9]({% post_url 2014-04-02-09-guessing-game-one %}))

{% highlight python %}
	import datetime
{% endhighlight %}

Now, we can use the `datetime` library to construct dates and manipulate them. The [full documentation for `datetime`](https://docs.python.org/3/library/datetime.html) has a comprehensive list of functions available in this library, but I will highlight a few common ones.

### Today's date

To get today's date, use the utility function:

{% highlight python %}
	>>> datetime.datetime.now()
	datetime.datetime(2022, 2, 19, 18, 40, 45, 276070)
{% endhighlight %}

which returns a `datetime` object that we can manipulate. For example:

{% highlight python %}
	>>> now = datetime.datetime.now()
	>>> now.year
	2022
	>>> now.month
	2
{% endhighlight %}

### Time Differences

We can also take the delta between two times:

{% highlight python %}
	>>> import datetime
	>>> import time
	>>> now = datetime.datetime.now()
	>>> time.sleep(2)
	>>> later = datetime.datetime.now()
	>>> later - now
	datetime.timedelta(seconds=2, microseconds=0)
{% endhighlight %}

_In the above sample code, we used `import time` from the Python [time](https://docs.python.org/3/library/time.html#time.sleep) library to pause the program for exactly 2 seconds._