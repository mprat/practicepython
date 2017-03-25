---
layout: post
title: Installing Python to Get Started
categories: [blog]
---

_Written by Michele Pratusevich._ One barrier to learning programming is getting your development environment set up. Whether you are on Windows, OSX, or Ubuntu, this guide will help you set up your computer with a basic Python installation so you can start your own journey with Python!

<!--more-->

"I haven't installed Python." "I don't want to mess up my computer by installing new software." "I have a Windows machine." I've heard all of these and more from readers as an excuse for not starting to learn Python. Never fear! Installing Python is a painless process for all 3 major operating systems (disclaimer: I haven't tried installing it on anything except Windows, OSX, and Ubuntu so I can't speak for any other system), and there are even installation-free alternatives if you just want to play around with basic syntax and code.

I'll go through my recommendations for installing Python on Windows, OSX, and Ubuntu, and then list a few no-installation-required options. You are not limited by your operating system!

# The ultimate Python installation recommendation

Whether you are on Windows, OSX, or Ubuntu, and want to quickly get started with Python, my recommendation is to install [Anaconda Python](https://www.continuum.io/downloads). The company that distributes Anaconda specifically packages Python and a few useful libraries, such as [Numpy](http://www.numpy.org/) and [Scipy](http://scipy.org) into an easy installer. It will create a desktop icon for Python, and will install a tool called `conda` that you can then use to install any extra Python packages you need.

Another benefit: you don't need administrative permissions! You can install Anaconda anywhere you have write permissions, such as your user's home directory.

You can read the official Anaconda installation recommendations [on their docs page](https://conda.io/docs/install/full.html). It's as easy as downloading and running the installer!

# Windows

You can't write your program in Microsoft Word. What you need is a text editor - a program that lets you edit text (programs!) without getting in your way. On Windows, you can use regular old Notepad, or a souped-up free version called [Notepad++](https://notepad-plus-plus.org/). You can also install my favorite text editor, [Sublime Text](https://www.sublimetext.com/3), on Windows. Regardless of which editor you use, you can run your 

If you can't install packages on your Windows computer because it is a shared computer, check out the section on [options where you don't need to install anything](#no-installation-required).

# OSX

For text editors, OSX comes with Xcode, but I recommend using a text editor like [Sublime Text](https://www.sublimetext.com/3), which you can download for free. 

For those who will be doing more serious Python development or want to use the command-line to install Python, I recommend doing the following (not for the faint of heart):

1. Install [Homebrew](https://brew.sh/) using the instructions on their website. Homebrew calls itself "the missing package manager for OSX" - it is definitively the easiest way to install and maintain software for development on OSX.
2. Do `brew install python3`. (You're using Python 3, right?)

Now you can run Python from the command line by running `python3` to get a Python shell, or writing a Python program in a text editor and running `python3 MyProgram.py`. To install Python packages, you run `pip3 install PACKAGE_NAME` on the command line.

# Ubuntu

Yep, you can install Anaconda Python for Ubuntu as well. It's a great option, even for experienced terminal users.

But if you don't want to use Anaconda, you can use `apt` to install Python 3:

{% highlight bash %}
sudo apt-get install python3
{% endhighlight %}

Then, to write Python programs, use your favorite text editor (have you guessed that my favorite is [Sublime Text](https://www.sublimetext.com/3)?), and run your Python programs by doing

{% highlight bash %}
python3 MY_PYTHON_FILE.py
{% endhighlight %}

`apt` also installs `pip3`, which is the Python-recommended way of installing Python packages. So if you want to install `numpy`, you would do 

{% highlight bash %}
pip3 install numpy
{% endhighlight %}

And it will install `numpy` to let you write `import numpy` at the top of your Python programs.

# No installation required

If you can't (or don't want to) install Python on your computer, there are a number of options for learning to code in Python that don't require installing any software. You can even do some of these options from an iPad or Android/Windows tablet!

My list is not comprehensive, and if you find another solution out there that works for you, please [email me and let me know](mailto:mail@practicepython.org).

* [Python Tutor](http://pythontutor.com/live.html#mode=edit) - Created by a friend and former colleague at MIT, Python Tutor lets you write Python in the cloud, and will even visualize the internals of the code for you. If you are the kind of person that learns visually or wants to see exactly what is happening in the background, I could not recommend Python Tutor more. Be warned, the functionality is very limited, but using Python Tutor should get you through the first 10 or so exercises on Practice Python.
* [repl.it](https://repl.it/languages/python3) - A cloud-based Python3 editor that lets you write and run code directly in your browser. You can even sign up for an account with Gmail, Github, or Facebook, to save and go back to your work. This platform is great for getting started, but it might not have all the packages installed that you want to use.
* [Python Fiddle](http://pythonfiddle.com/) - Based off of JSFiddle, PythonFiddle lets you write and run small programs in your web browser. Same deal as with repl.it - they might not have all the packages you need, but it will definitely get you started.
* [Cloud 9](https://c9.io/) - If you are more of a developer-type and want a more hardcore online development environment, Cloud 9 lets you basically set up a virtual machine in the cloud. You can use it to install any custom packages and run any custom code you want. I wouldn't recommend this as a place to start, but if you want a Linux (Ubuntu) environment you have lots of control over and want to be able to install any packages you want, it is worth looking into.

While using browser-based editors is fantastic for learners and casual coders, if you are going to be doing any serious data processing or multi-file coding, I suggest you install Python on a computer so you can have more control and processing power on your local machine. 

# Final thoughts

Your environment doesn't matter - if you want to learn how to program, solve logic problems, and think analytically, there are many options out there for you! Just pick one and get started.

[Here is a link to the first exercise on Practice Python. Start coding!]({{ site.baseurl }}{% post_url 2014-01-29-01-character-input %})
