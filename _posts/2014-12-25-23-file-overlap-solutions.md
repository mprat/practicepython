---
layout: post
number: 23
categories: [solution]
published: True
---

## [Exercise]({{ site.baseurl }}{% post_url 2014-12-14-23-file-overlap %})


Given two `.txt` files that have lists of numbers in them, find the numbers that are overlapping. [One `.txt` file]({{ site.url }}/assets/primenumbers.txt) has a list of all prime numbers under 1000, and [the other `.txt` file]({{ site.url }}/assets/happynumbers.txt) has a list of happy numbers up to 1000.

(If you forgot, prime numbers are numbers that can't be divided by any other number. And yes, happy numbers are a real thing in mathematics - you can [look it up on Wikipedia](http://en.wikipedia.org/wiki/Happy_number). The explanation is easier with an example, which I will describe below.)


## Sample solution 

For a simple look at the solution (without using functions and using a `for` loop), look no further. Read on for a solution using functions and list comprehensions, along with a detailed explanation in Python 3. 

### The solution without functions using a `for` loop (read on for the one with functions and the explanation) 

{% gist mprat/897b63094f3b702e4d9e files_overlap_nofunctions.py %}

### The solution with functions using list comprehensions (read on for the explanation)

{% gist mprat/897b63094f3b702e4d9e files_overlap_functions.py %}

### The explanation

The interesting thing about this problem is that it is an extension of a [previous exercise asking to find the overlap of two lists]({{ site.baseurl }}{% post_url 2014-03-05-05-list-overlap %}). Instead of lists that are hard-coded into the file, the program will now read lists of information from files somewhere on the computer and perform the same overlap operation. 

The first thing to do is open the `.txt` files and save them somewhere on your computer (easiest is in the same folder as the Python file you are working in). You notice that when you look at the file, each line of the file is an integer. Next, in Python we want to open one of the files and save the contents (as integers) into a list. 

This code snippet, as taken from the [Exercise 23 explanation about reading from files]({{ site.baseurl }}{% post_url 2014-12-14-23-file-overlap %}), will open the file and print out all the lines.

{% highlight python %}
  with open('primenumbers.txt') as f:
  	line = f.readline()
  	while line:
  		print(line)
  		line = f.readline()
{% endhighlight %}

We now want to just save each line as a separate integer into the list.

{% highlight python %}
  primeslist = []
  with open('primenumbers.txt') as f:
  	line = f.readline()
  	while line:
  		primeslist.append(int(line))
  		line = f.readline()
{% endhighlight %}

All we did was change the `print` into an `append` to the list, and make an empty list at the beginning. Note that before I append the `line` to my list, I turn it into an `int` with the `int()` statement.

Now we have a choice. We can either do this twice (copy and paste the exact same code), or write a function to do this for us whenever we want. 

Let's make this into a function, for explanation's sake. What we want to do here is make a function that I give the name of the file to, and it gives back to me a list of all the numbers in that file, assuming each line contains a separate integer. We need to add two lines to our code snippet from above, the _function header_ and the _return statement_. The _function header_ is just the name of the function with the list of variables to return, and the _return statement_ is the line `return list_of_ints` at the end of the function. 

{% highlight python %}
  def filetolistofints(filename):
	  list_of_ints = []
	  with open(filename) as f:
	  	line = f.readline()
	  	while line:
	  		list_of_ints.append(int(line))
	  		line = f.readline()
	  return list_of_ints
{% endhighlight %}

Now I can use this function to read both of my files in two simple lines: 

{% highlight python %}
  primeslist = filetolistofints('primenumbers.txt')
  happieslist = filetolistofints('happynumbers.txt')
{% endhighlight %}

What I have now in my variables `primeslist` and `happieslist` are lists where each element was a number on a separate line in each of the files. 

My last step is to find the overlap between them. I can either use two `for` loops or a _list comprehension_. (If you need a refresher, [Exercise 3]({{ site.baseurl }}{% post_url 2014-02-15-03-list-less-than-ten %}) talks about `for` loops and [Exercise 7]({{ site.baseurl }}{% post_url 2014-03-19-07-list-comprehensions %}) talks about list comprehensions.)

As a list comprehension, you construct a new list that takes each element from `primeslist` and only adds it to our new list if it is inside `happieslist`. 

{% highlight python %}
  overlaplist = [elem for elem in primeslist if elem in happieslist]
{% endhighlight %}

This can also be done with a for loop, as below: 

{% highlight python %}
  overlaplist = []
  for elem in primeslist:
    if elem in happieslist:
      overlaplist.append(elem)
{% endhighlight %}

And when the loop is done, `overlaplist` will contain all the elements of the overlap.  

Now we can just print our result (using Python 3 syntax) and be done. 

{% highlight python %}
  print(overlaplist)
{% endhighlight %}

For a full and concise solution once again, here it is: 

{% gist mprat/897b63094f3b702e4d9e files_overlap_functions.py %}

Happy hacking!