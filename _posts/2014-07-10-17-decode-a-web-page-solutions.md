---
layout: post
number: 17
categories: [solution]
---

The [How To Decode A Website]({{ site.baseurl }}{% post_url 2014-06-06-17-decode-a-web-page %}) exercise was a challenging one, involving many complex pieces of code and two new Python modules. When appropaching problems like this one, it helps to develop a plan for the program before executing it. 

Our plan should be as follows: 

1. Use the `requests` library to load the HTML of the page into Python
2. Set up BeautifulSoup to process the HTML
3. Find out which HTML tags contain all the titles
4. Use BeautifulSoup to extract all the titles from the HTML
5. Format them nicely

We will go through each of these steps in this detailed description.

First, take a look at the full program without any comments:

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

Next we need to figure out what exactly we need to look for in the HTML decoding of the New York Times webpage. I will explain how to do this in the Chrome browser - it works in other browsers but the instructions may be slightly different. Right-click on the page, and click "Inspect Element." Like so: 

<figure class="twocol-figure">
  <img src="{{ site.baseurl }}/assets/img/inspect_element.png" width="100%">
  <figcaption>Figure 1: How to Inspect the HTML on a Page</figcaption>
</figure>

What pops up at the bottom of the page contains all the HTML that makes up the page. Let us now find the HTML that exactly describes the headlines of the main page. Pick a headline - let's take "Germans Order Expulsion of Top U.S. Spy in Espionage Case". Now click the magnifying glass at the bottom of the page: 

<figure class="twocol-figure">
  <img src="{{ site.baseurl }}/assets/img/magnifying_glass.png" width="100%">
  <figcaption>Figure 2: The Magnifying Glass</figcaption>
</figure>

And move the mouse to click on the title we chose. You can see that at the bottom of the page in the HTML bar, we see the line 

{% highlight html %}
  <h2 class="story-heading"> .. </h2>
{% endhighlight %}

<figure class="twocol-figure">
  <img src="{{ site.baseurl }}/assets/img/story-heading.png" width="100%">
  <figcaption>Figure 3: Find the CSS Class</figcaption>
</figure>

Our working assumptions for the moment is that all of the story titles are embedded inside some kind of HTML tag with a class called `story-heading`. Confirm with another title or two to make sure this assumption is correct, which it is. 

Now that we know we are looking for all elements on the page with the class `story-heading`, so we need to find the [documentation for how to do that](http://www.crummy.com/software/BeautifulSoup/bs4/doc/#find-all), with [special instructors for how to do this for a class](http://www.crummy.com/software/BeautifulSoup/bs4/doc/#searching-by-css-class). We end up with: 

{% highlight python %}
  soup.find_all(class_="story-heading")
{% endhighlight %}

This returns a list of all tags with `story-heading` as a class. What we need to do is loop through all of them with a `for` loop and see what format the output is in. 

{% highlight python %}
  for story_heading in soup.find_all(class_="story-heading"):
    print(story_heading)
{% endhighlight %}

{% highlight pycon %}
  <h2 class="story-heading">...
{% endhighlight %}

If you scroll through the list of outputs, they come in two varieties: 

1. Links
2. Not links

When we loop through the lines with `story-heading`, we need to take this difference into account using more [BeautifulSoup magic](http://www.crummy.com/software/BeautifulSoup/bs4/doc/#quick-start): 

{% highlight python %}
   for story_heading in soup.find_all(class_="story-heading"): 
    if story_heading.a: 
        print(story_heading.a)
    else: 
        print(story_heading)
{% endhighlight %}

To see this output: 

{% highlight pycon %}
  <a href="http://www.nytimes.com/2014/07/11/...
{% endhighlight %}

And then remove the text from the link and the title from the list of contents: 

{% highlight python %}
   for story_heading in soup.find_all(class_="story-heading"): 
    if story_heading.a: 
        print(story_heading.a.text)
    else: 
        print(story_heading.contents[0])
{% endhighlight %}

{% highlight pycon %}
  Germans Order Expulsion of Top U.S. Spy in Espionage Case
  Death Toll Rises in Gaza, as Hamas Hits New Targets in Israel
  ...
{% endhighlight %}

We are almost there! The only thing missing is the formatting - if you scroll through the list of outputs, the formatting of some titles farther down the list. There are an excess of spaces, so stripping the strings and replating all instances of new lines and tabs with regular spaces should do the trick. Take a look at the [Python string methods documentation](https://docs.python.org/3.3/library/stdtypes.html). 

And this is how we get lines 8 through 12:

{% highlight python %}
  for story_heading in soup.find_all(class_="story-heading"): 
    if story_heading.a: 
        print(story_heading.a.text.replace("\n", " ").strip())
    else: 
        print(story_heading.contents[0].strip())
{% endhighlight %}

And we have our list of titles!

{% highlight pycon %}
  Germans Order Expulsion of Top U.S. Spy in Espionage Case
  Death Toll Rises in Gaza, as Hamas Hits New Targets in Israel
  ...
{% endhighlight %}

Take a look the full program with all it's comments here:
{% gist mprat/df2969142a75b668456c decode-web-page-comments.py %}

## User-submitted solutions

Here are some user solutions!

<script src="https://gist.github.com/anonymous/6470881a65877c2f3e83.js"></script>
