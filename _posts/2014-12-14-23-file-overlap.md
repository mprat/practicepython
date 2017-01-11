---
layout: post
number: 23
chili: 2
categories: [exercise]
published: True
---

{% include exercise_header.md number=page.number %}

Given two `.txt` files that have lists of numbers in them, find the numbers that are overlapping. [One `.txt` file]({{ site.url }}/assets/primenumbers.txt) has a list of all prime numbers under 1000, and [the other `.txt` file]({{ site.url }}/assets/happynumbers.txt) has a list of happy numbers up to 1000.

(If you forgot, prime numbers are numbers that can't be divided by any other number. And yes, happy numbers are a real thing in mathematics - you can [look it up on Wikipedia](http://en.wikipedia.org/wiki/Happy_number). The explanation is easier with an example, which I will describe below.)

## Discussion

You'll need to stitch together a few ideas of things I've previously talked about on this blog, so if you need a refresher in any of these topics, now is your chance! Of course, there are any number of ways to do this exercise, so these are only suggestions.

Topics: 

1. Reading a file, in [Exercise 21]({{ site.baseurl }}{% post_url 2014-12-06-22-read-from-file %})
2. Number types and converting to integers from strings, in [Exercise 1]({{ site.baseurl }}{% post_url 2014-01-29-01-character-input %})
3. Lists, in [Exercise 3]({{ site.baseurl }}{% post_url 2014-02-15-03-list-less-than-ten %}) and [Exercise 5]({{ site.baseurl }}{% post_url 2014-03-05-05-list-overlap %})


Enjoy!

{% include submit.md %}