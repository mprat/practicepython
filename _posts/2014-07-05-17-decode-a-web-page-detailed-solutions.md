---
layout: post
number: 17
tags: [solution]
---

The [How To Decode A Website]({% post_url 2014-06-06-17-decode-a-web-page %}) exercise was a challenging one, involving many complex pieces of code and two new Python modules. When appropaching problems like this one, it helps to develop a plan for the program before executing it. 

INSERT PLAN FOR THE PROGRAM

No comments on full program: 

{% gist mprat/df2969142a75b668456c decode-web-page-no-comments.py %}

Let us break this down piece by piece and line by line. 

Line 1: 

{% highlight python %}
	import requests
{% endhighlight %}

First, install the `requests` library according to [the official documentation](http://docs.python-requests.org/en/latest/) and your operating system, then import the library into the program.

Next, 

{% highlight python %}
	from bs4 import BeautifulSoup
{% endhighlight %}

Install `BeautifulSoup` according to the [installation documentation](http://www.crummy.com/software/BeautifulSoup/bs4/doc/#installing-beautiful-soup). Importing the library is not like the usual way of `import foo`. Reading the [import / useage documentation](http://www.crummy.com/software/BeautifulSoup/bs4/doc/#making-the-soup) is the right approach.

Next: 

{% highlight python %}
	base_url = 'http://www.nytimes.com'
	r = requests.get(base_url)
{% endhighlight %}

These lines make the request to the New York Times homepage. Making a request is simple, according to the [documentation](http://docs.python-requests.org/en/latest/user/quickstart/#make-a-request) you supply a URL and make a GET request.

{% highlight python %}
	soup = BeautifulSoup(r.text)
{% endhighlight %}

Reading further through the documentation, we discover that `r`, contains all the information from the request sent to the New York Times homepage. What we actually want is to look at the HTML of the page and analyze it, so we find that `r.text` returns all the HTML from the returned request.

After this, BeautifulSoup is the tool we use to recode the HTML. In [the same documentation](http://www.crummy.com/software/BeautifulSoup/bs4/doc/#making-the-soup) that describes how to import BeautifulSoup, it describes how to import the HTML to analyze it in Python using the line of code in line 6.

Next we need to figure out what exactly we need to look for in the HTML decoding of the New York Times webpage. The way to start is to look at the HTML of the webpage to find the pattern we are looking for. The way to do that is to go to the actual website and look at the HTML. 





Take the full program with all it's comments here:
http://docs.python-requests.org/en/latest/
{% gist mprat/df2969142a75b668456c decode-web-page-comments.py %}