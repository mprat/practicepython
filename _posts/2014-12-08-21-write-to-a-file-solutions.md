---
layout: post
number: 21
categories: [solution]
published: True
---

## [Exercise {{ page.number }}]({{ site.baseurl }}{% post_url 2014-11-30-21-write-to-a-file %})

Take the code from the [How To Decode A Website]({{ site.baseurl }}{% post_url 2014-06-06-17-decode-a-web-page %}) exercise (if you didn't do it or just want to play with some different code, use the code from the [solution]({{ site.baseurl }}{% post_url 2014-07-10-17-decode-a-web-page-solutions %})), and instead of printing the results to a screen, write the results to a txt file. In your code, just make up a name for the file you are saving to.

Extras:

* Ask the user to specify the name of the output file that will be saved.

## Sample solution 

The sample solution takes the out-of-the-box solution for [Exercise 17](https://gist.github.com/mprat/b042a834835cfb4bbe6c) and adds two components: 

1. Asking the user for the name of a file 
2. Substitutes every `print` statement with a statement writing to a file

Here is the full solution: 

{% gist mprat/068d1e6d10e01baf44cd write-to-a-file-solutions.py %}