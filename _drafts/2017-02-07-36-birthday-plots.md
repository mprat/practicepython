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

In this exercise, use the [bokeh]() Python library to plot a histogram of which months the scientists have birthdays in! Because it would take a long time for you to input the months of various scientists, you can use [my scientist birthday JSON file](). Just parse out the months (if you don't know how, I suggest looking at the [previous exercise]({{ site.baseurl }}{% post_url 2017-01-31-35-birthday-months %}) or [it's solution]()) and draw your histogram.

If you are using a purely web-based interface for coding, this exercise won't work for you! Now might be a good time to [install Python on your own computer]().

# Discussion

Today's topic is going to be about the [bokeh]() Python library. Sometimes it is really nice to write code or algorithms from scratch to learn and practice. And sometimes, someone has already written the code so well that you should use theirs. Bokeh is one of these libraries - it is library specifically with functions for making plots, based on the famous [D3.js]() library originally developed at the New York Times for their visualizations.

## Plotting libraries in Python

If you are looking for a plotting library in Python, you have two main options: [matplotlib]() and [bokeh](). Today I want to discuss bokeh, because I think it will become more popular in years to come.

Many Python developers (and especially data scientists and researchers) will tell you that the most commonly used plotting library in Python is [matplotlib](). I myself was a matplotlib user for many years - the integrations with Python data libraries are great, and migrating from the MATLAB plotting environment to matplotlib is easy. But a friend introduced me to bokeh and I was hooked ever since. Because it is based on D3.js, the visualizations look smooth and professional.

There is no one "best" plotting library - you should use whichever one feels and looks better for you.

## When to make plots

We use plots to convey information. From this histogram:

INSERT SOME IMAGE HERE

you can immediately see that you spent the most money in December. From this graph:

INSERT SOME IMAGE HERE

you can immediately see that the <SOME INCOME OR GENDER THING>

So learning how to make plots will help you become better at displaying and communicating information, both to yourself and to others.

## Installing bokeh

To use bokeh, we first have to install it. Unlike something like [`json`]() or [`Counter`]() from previous exercises, bokeh does not come installed with Python.

If you are using the [Anaconda Python]() distribution (which you should, if you are on Windows!) then you can install bokeh by typing 

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

So the first thing you have to do is prepare some data. Usually, when you are plotting data you have two axes, or groups of data, an x-axis (or horizontal axis) and a y-axis (or vertical axis). 

* make a bar plot using bokeh of the months in which people have birthdays
