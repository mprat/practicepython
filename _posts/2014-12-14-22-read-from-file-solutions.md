---
layout: post
number: 22
categories: [solution]
published: True
---

## [Exercise {{ page.number }}]({{ site.baseurl }}{% post_url 2014-12-06-22-read-from-file %})

Given a `.txt` file that has a list of a bunch of names, count how many of each name there are in the file, and print out the results to the screen. I have a `.txt` file for you, if you want to [use it]({{ site.url }}/assets/nameslist.txt)!

Extra:

* Instead of using the `.txt` file from above (or instead of, if you want the challenge), take [this `.txt` file]({{ site.url }}/assets/Training_01.txt), and count how many of each "category" of each image there are. This text file is actually a list of files corresponding to the [SUN database](http://sundatabase.mit.edu) scene recognition database, and lists the file directory hierarchy for the images. Once you take a look at the first line or two of the file, it will be clear which part represents the scene category. To do this, you're going to have to remember a bit about string parsing in Python 3. I talked a little bit about it [in this post]({{ site.baseurl }}{% post_url 2014-03-12-06-string-lists %}).


## Sample solution 

The basics of reading any file is that you need to read each line one by one, only reading the next line if the next line exists. The skeleton code for this operation is shown here: 

{% highlight python %}
  with open('filename.txt') as f:
  	line = f.readline()
  	while line:
  		print(line)
  		line = f.readline()
{% endhighlight %}

Basically, after you open the file, read one line at a time. Then, check if the line exists using the statement `while line`, and if it does, get the next line. What happens when the next time `line = f.readline()` is called and there is no next line? `while line` the next time around in the loop will return `False` and the code stops.

Given this skeleton, the first solution counts the different names in the `nameslist.txt` file.

{% gist mprat/f2896e03c3980e0c3654 read_from_file_small_example.py %}

The line `line = line.strip()` takes the string read in from the line and gets rid of all whitespaces (including the `\n` character). And the basic construction and update of the dictionary is very common in many applications.

The second counts how many of each category of image there are in the `Training_01.txt` file from the [SUN image database](http://sundatabase.mit.edu).

{% gist mprat/f2896e03c3980e0c3654 read_from_file_sun.py %}