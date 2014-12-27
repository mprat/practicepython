---
layout: post
number: 24
chili: 2
categories: [exercise]
published: True
---

## Exercise

Time for some fake graphics! Let's say we want to draw game boards that look like this: 

{% highlight python %}
	 --- --- --- 
	|   |   |   | 
	 --- --- ---  
	|   |   |   | 
	 --- --- ---  
	|   |   |   | 
	 --- --- --- 
{% endhighlight %}

This one is 3x3 (like in tic tac toe). Obviously, they come in many other sizes (8x8 for chess, 19x19 for Go, and many more).

Ask the user what size game board they want to draw, and draw it for them to the screen using Python's `print` statement. 

Remember that in Python 3, printing to the screen is accomplished by

{% highlight python %}
  print("Thing to show on screen")
{% endhighlight %}

_Hint: this requires some use of functions, as were discussed [previously on this blog]({{ site.baseurl }}{% post_url 2014-04-16-11-check-primality-functions %}) and [elsewhere on the Internet, like this TutorialsPoint link](http://www.tutorialspoint.com/python/python_functions.htm)._

## Topics and links for more information

The main topic of this exercise is functions. They are tricky, and deserve lots of practice and thought. Here are a few links in case you want some more reading.

1. [Functions on TutorialsPoint](http://www.tutorialspoint.com/python/python_functions.htm)
2. [Hands-on Python, by Loyola University](http://anh.cs.luc.edu/python/hands-on/3.1/handsonHtml/functions.html)
3. [Learn Python the Hard Way](http://learnpythonthehardway.org/book/ex21.html)
4. [ZetCode](http://zetcode.com/lang/python/functions/)

There are hundreds more out there - read and practice away!


Happy Coding!

{% include submit.md %}