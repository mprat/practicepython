---
layout: post
number: 36
chili: 3
part: 4
of: 4
part_text: birthday data
categories: [exercise]
---

{% include exercise_header.md number=page.number %}

{% include parts_sentence.md part=page.part part_text=page.part_text part_of=page.of %} 

In the [previous exercise]({{ site.baseurl }}{% post_url 2017-01-31-35-birthday-months %}) we counted how many birthdays there are in each month in our dictionary of birthdays.

In this exercise, use the [bokeh](http://bokeh.pydata.org/en/latest/) Python library to plot a histogram of which months the scientists have birthdays in! Because it would take a long time for you to input the months of various scientists, you can use [my scientist birthday JSON file]({{ site.baseurl }}/assets/scientist_birthdays.json). Just parse out the months (if you don't know how, I suggest looking at the [previous exercise]({{ site.baseurl }}{% post_url 2017-01-31-35-birthday-months %}) or [its solution]()) and draw your histogram.

If you are using a purely web-based interface for coding, this exercise won't work for you! Now might be a good time to [install Python on your own computer]().

# Discussion

Today's topic is going to be about the [bokeh](http://bokeh.pydata.org/en/latest/) Python library. Sometimes it is really nice to write code or algorithms from scratch to learn and practice. And sometimes, someone has already written the code so well that you should use theirs. Bokeh is one of these libraries - it is library specifically with functions for making plots, based on the famous [D3.js](https://d3js.org/) library originally developed at the New York Times for their visualizations.

## Plotting libraries in Python

If you are looking for a plotting library in Python, you have two main options: [matplotlib](http://matplotlib.org/) and [bokeh](http://bokeh.pydata.org/en/latest/). Today I want to discuss bokeh, because I think it will become more popular in years to come.

Many Python developers (and especially data scientists and researchers) will tell you that the most commonly used plotting library in Python is [matplotlib](http://matplotlib.org/). I myself was a matplotlib user for many years - the integrations with Python data libraries are great, and migrating from the MATLAB plotting environment to matplotlib is easy. But a friend introduced me to bokeh and I was hooked ever since. Because it is based on D3.js, the visualizations look smooth and professional.

There is no one "best" plotting library - you should use whichever one feels and looks better for you.

## When to make plots

We use plots to convey information. From this histogram:

![US Government spending hitsogram]({{ site.baseurl }}/assets/imgs/united-states-government-spending.png)

you can immediately see that the US government spending has been steadily increasing, reaching a peak in January 2017.

So learning how to make plots will help you become better at displaying and communicating information, both to yourself and to others.

## Installing bokeh

To use bokeh, we first have to install it. Unlike something like [`json`](https://docs.python.org/3/library/json.html) or [`Counter`](https://docs.python.org/3/library/collections.html#collections.Counter) from previous exercises, bokeh does not come installed with Python.

If you are using the [Anaconda Python](https://www.continuum.io/downloads) distribution (which you should, if you are on Windows!) then you can install bokeh by typing 

{% highlight bash %}
conda install bokeh
{% endhighlight %}

in the Windows command prompt or the bash shell.

On OSX or GNU / Linux, just type

{% highlight bash %}
pip install bokeh
{% endhighlight %}

(If you have Python 2 and Python 3 installations side by side you might have to do `pip3 install bokeh` to specifically install it for Python 3.)

## Using bokeh

The basic idea of any plotting package is simple:

1. Load the data
2. Display the data

So the first thing you have to do is prepare some data. Usually, when you are plotting data you have two axes, or groups of data, an x-axis (or horizontal axis) and a y-axis (or vertical axis). The `x` variable is your input (independent) variable and the `y` variable is your output (dependent) axis.

For use in bokeh, your data should be loaded into two separate lists, one for the x-axis and one for the y-axis. The basic format of a bokeh (in this case histogram) looks like this:

{% highlight python %}
# need to import at least 3 things to make your
# bokeh plots work
from bokeh.plotting import figure, show, output_file

# we specify an HTML file where the output will go
output_file("plot.html")

# load our x and y data
x = [10, 20, 30]
y = [4, 5, 6]

# create a figure
p = figure()

# create a histogram
p.vbar(x=x, top=y, width=0.5)

# render (show) the plot
show(p)
{% endhighlight %}

The way bokeh outputs plots is really cool: when you run a piece of bokeh code, it outputs the result into an HTML file that you can then save and display in a web browser on it's own. After you run this segment on top, it will automatically open a web browser and show you a plot.

The example above works when x is a numerical value. But, in the exercise, we are dealing with months, which is called a "categorical" variable (i.e. it belongs to a category, and is not continuous). To make sure bokeh draws the axis correctly, you need to specify a special call to `figure()` to pass an `x_range`, like so:

{% highlight python %}
from bokeh.plotting import figure, show, output_file

output_file("plot.html")
x_categories = ["a", "b", "c", "d", "e"]
x = ["a", "d", "e"]
y = [4, 5, 6]

p = figure(x_range=x_categories)
p.vbar(x=x, top=y, width=0.5)

show(p)
{% endhighlight %}

There are also extra commands and arguments you can pass to bokeh to display an title for the plot, for each of the axis, for the color of the bars, and so on.

If you want to dive deep into that documentation, check out these resources:

* [Bar plots / histograms](http://bokeh.pydata.org/en/latest/docs/user_guide/plotting.html#bars)
* [Categorical axes](http://bokeh.pydata.org/en/latest/docs/user_guide/plotting.html#categorical-axes)
* [Everything to do with styling plots](http://bokeh.pydata.org/en/latest/docs/user_guide/styling.html)
* [Basic plotting for other types of graphs](http://bokeh.pydata.org/en/latest/docs/user_guide/plotting.html)

If you want to add more flair to your histogram from this exercise, there are many resources on the web to help you out!

Happy coding!
