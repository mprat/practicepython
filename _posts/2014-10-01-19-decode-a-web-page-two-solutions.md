---
layout: post
number: 19
categories: [solution]
---

{% include solution_header.md number=page.number %}

The [How To Decode A Web Page Two]({{ site.baseurl }}{% post_url 2014-07-14-19-decode-a-web-page-two %}) exercise was a follow-up to the extremely challenging prelude, [How To Decode A Web Page]({{ site.baseurl }}{% post_url 2014-06-06-17-decode-a-web-page %}). The purpose of the original (and the follow-up exercise) was to give people a chance to poke around at a close-to-real application of Python. 

A few people submitted solutions to this exercise (one example is given at the bottom of the page), and many of them used things that I haven't yet talked about in the exercises. I will not go into extreme detail about how to solve this problem - I will just present the important points for one way you could solve this problem. For a more detailed solution to a similar problem, I encourage you to look at the [solution to the previous exercise (How To Decode A Web Page)]({{ site.baseurl }}{% post_url 2014-07-10-17-decode-a-web-page-solutions %}).

And without further ado, a plan for achieving the solution:

1. Use the `requests` library to load the HTML of the page into Python
2. Find out which HTML tags contain the article text
2. Use `BeautifulSoup` to process HTML and extract the text of the article
3. Print the extracted text to the screen

In my opinion, the difficult part of this exercise is figuring out the elements on the page (whether that is through HTML or CSS selectors) that contain all the text of the article. It requires knowing or exploring a little bit about CSS selectors and reading documentation. Such is the way of working with web pages.

A few observations on that point:

* The entire text of the article is on this single page - no need to move to another URL. The text is placed inside "hidden containers" that are just set to invisible. 
* It seems that article text comes inside `p` elements that are inside `div` elements of class `body` that are inside `div` elements that have classes `parbase` and `cn_text`. But it also seems that there are other things like hyperlinks and article comments also fall inside this structure. 
* When you select for this in `BeautifulSoup`, the first 7 elements that come out are links and the introduction, so we just want to ignore those.

Given these observations, this solution:

<script src="https://gist.github.com/mprat/6ccebfa546f72488c5ec.js"></script>

prints to the screen the full text of the article.

The CSS selectors are complex, and it takes some practice to get comfortable with them. We'll re-visit this later (perhaps much later), but for now I encourage you to poke around the internet and look at sources of websites, playing with `BeautifulSoup` and figuring out how CSS selectors behave.

Here is an example of a user-submitted solution that is not completely automated, and that does not use the exact article specified. However, it does show you that you can start solving your own problems using the techniques I am talking about on this blog.

<script src="https://gist.github.com/anonymous/b5d1287a09aa6fa555a8.js"></script>


