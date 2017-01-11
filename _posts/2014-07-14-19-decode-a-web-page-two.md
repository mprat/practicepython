---
layout: post
number: 19
chili: 4
categories: [exercise]
---

{% include exercise_header.md number=page.number %}

Using the `requests` and `BeautifulSoup` Python libraries, print to the screen the full text of the article on this website: [http://www.vanityfair.com/society/2014/06/monica-lewinsky-humiliation-culture](http://www.vanityfair.com/society/2014/06/monica-lewinsky-humiliation-culture). 

The article is long, so it is split up between 4 pages. Your task is to print out the text to the screen so that you can read the full article without having to click any buttons.

(_Hint: The post [here]({{ site.baseurl }}{% post_url 2014-07-10-17-decode-a-web-page-solutions %}) describes in detail how to use the `BeautifulSoup` and `requests` libraries through the solution of the exercise posted [here]({{ site.baseurl }}{% post_url 2014-06-06-17-decode-a-web-page %})._)

This will just print the full text of the article to the screen. It will not make it easy to read, so next exercise we will learn how to write this text to a `.txt` file. 

## Discussion

### Inspecting HTML on a web page

If you have forgotten how to inspect the HTML of a web page, look at the [detailed solution to the previous exercise]({{ site.baseurl }}{% post_url 2014-06-06-17-decode-a-web-page %}) for a very detailed explanation. In brief: 

1. Open the web page in Chrome.
2. Right-click the page and click "Inspect Element"
3. Use the magnifying glass on the bottom-left of the page to click on elements of the page and look at their properties.

{% include submit.md %}