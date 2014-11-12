---
layout: post
number: 21
chili: 1
categories: [exercise]
published: False
---

## Exercise

Take the code from the [How To Decode A Website]({{ site.baseurl }}{% post_url 2014-06-06-17-decode-a-web-page %}) exercise (if you didn't do it or just want to play with some different code, use the code from the [solution]({{ site.baseurl }}{% post_url 2014-07-10-17-decode-a-web-page-solutions %})), and instead of printing the results to a screen, write the results to a txt file. In your code, just make up a name for the file you are saving to.

Extras:

* Ask the user to specify the name of the output file that will be saved.

## Discussion

Topics: 

1. Writing to a file
2. Gotchas and warnings

### Saving to a file

Python makes it very easy to write to a file. Depending on what kind of file you want to write to and what kind of data you are writing, your options are plenty. I will show you the simplest form of writing to a file - writing plain text to a plain old text file. In other words, writing a string to a `.txt` file.

The code looks like this: 

{% highlight python %}
  with open('file_to_save.txt', 'w') as open_file:
    open_file.write('A string to write')
{% endhighlight %}

An alternate way of writing the same code is like so:

{% highlight python %}
  open_file = open('file_to_save.txt', 'w')
  open_file.write('A string to write')
  open_file.close()
{% endhighlight %}

The first is considered better programming practice, but the second might explain a little bit better what is going on in the first code sample.

Let's go through line by line. 

The `with open('file_to_save.txt', 'w') as open_file` syntax is new for us - all it means is that inside the code block indented underneath, there will be a variable called `open_file` that will represent the file object. You can pick any name for this file - it is just a variable name. The `open()` function takes two arguments - the first is the name of a file as a string (if the file does not exist, Python will create it), and a second argument that represents _how_ the file should be opened. There are a few ways you can open files (read all about it [at the official Python documentation](https://docs.python.org/3.3/tutorial/inputoutput.html#reading-and-writing-files)), but in short, there are two most common ones: `'r'` and `'w'`. `'r'` stands for "read only" and `'w'` stands for "write only" (you can open for both read and write using `'r+'`). You should tell Python which way you want to open the file - you don't want to modify a file you are only looking at, and opening a file with `'w'` when you want to only read it will overwrite the old file. 

When you open a file, it will look for it in the same directory as the Python program. If there is no file with that name, Python will create a file in that directory with the given name. To look for files in other directories, use the `../` notation to move up and down directories as necessary.

As soon as the program exists the `with` code block for any reason, it will close the file. In the second code example case, I created the file object by opening the file and saving the object to my variable `open_file`. I then had to remember to close the file manually at the end of my program. This is considered worse programming practice, because in case there is an error in the program and it terminates before hitting the `.close()` statement, there will be a floating open file object somewhere in memory. You do this enough times and it becomes a problem, especially for production environments. For playing around with Python, this is not usually a problem, but why not learn how to program correctly the first time?

The `write()` portion is simple - call `.write()` with a string (if something is not a string, turn it into a string first), and it will write to the end of the file.

When the program exists the `with` statement, the file will automatically be saved. In fact, every time after a `.write()` statement, the file will be automatically saved.

### Gotchas and Warnings

This all seems simple enough, but there are a few caveats to the file-writing endeavor. 

1. You always want to make sure you close a file. The easiest strategy for this is explained above - use the `with` statement rather than trying to manually remember to `.close()` the file.
2. Opening a file for writing with `'w'` will overwrite any file that currently exists with that name. If you have previously written data to that file, it is now gone as soon as Python opens it. 
3. You can write _any_ kind of object to any kind of file in Python, as long as you specify the correct format. The simplest thing to do is to write strings to a `.txt` file. But remember - you have to convert numbers or objects into strings before you write them to a file. In a later exercise, we'll talk about writing to other formats.

The best way to remember the caveats is to explore them yourself, so have at it!

{% include submit.md %}