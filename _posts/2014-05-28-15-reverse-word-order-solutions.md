---
layout: post
number: 15
tags: [solution]
---

## [Exercise]({% post_url 2014-05-21-15-reverse-word-order %})

Write a program (using functions!) that asks the user for a long string containing multiple words. Print back to the user the same string, except with the words in backwards order. For example, say I type the string: 

{% highlight python %}
  My name is Michele
{% endhighlight %}

Then I would see the string: 

{% highlight python %}
  Michele is name My
{% endhighlight %}

shown back to me.

## Sample solution

Here is the quick, one-liner solution to the problem: 

<script src="https://gist.github.com/anonymous/2baf03ac1147bf767455.js"></script>

But most likely you didn't come up with that solution right away. You most likely went through a number of iterations like this: 

<script src="https://gist.github.com/prgrm/06d70e6d0f2d03257e9c.js"></script>

But you also could have taken a hybrid approach: 

<script src="https://gist.github.com/Shad0walker/c8cd4e52d11c8e6aa3b5.js"></script>