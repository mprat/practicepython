---
layout: post
number: 11
categories: [exercise]
---

## Exercise

Ask the user for a number and determine whether the number is prime or not. (For those who have forgotten, a prime number is a number that has no divisors.). You can (and should!) use your answer to [Exercise 4]({% post_url 2014-02-26-04-divisors %} to help you. Take this opportunity to practice using functions, described below.

## Discussion

Concepts for this week:

* Functions
* Reusable functions
* Default arguments

### Functions

One of the tools programming gives us is the ability to break down problems into easier (or perhaps previously solved) or reusable subproblems. It is good practice to have a function have a single purpose, and the name of that function should hint at it's purpose in some way. 

Most programming languages have this idea of a function, subroutine, or subprogram. In Python, a function is a programming construct that allows exactly that.

Let's look at a simple example: 

{% highlight python %}
  def get_integer():
    return int(input("Give me a number: "))
{% endhighlight %}

In this small example, we used the same code that asks a user for input as a tabbed line underneath this `def` statement. The `def` means that everything tabbed underneath is a function. The name `get_integer()` is just a name that I (the programmer) made up. If I just include this code inside a Python file and run it, nothing will happen - all I have done so far is wrapped my code inside of a function; I never told my program to actually RUN my function.

{% highlight python %}
  def get_integer():
    return int(input("Give me a number: "))

  age = get_integer()
  school_year = get_integer()
  if age > 15:
    print("You are over the age of 15")
  print("You are in grade " + str(school_year))
{% endhighlight %}

What I have done here is *called* the function (told it to run) by writing `age = get_integer()`. When this line of code runs, what happens is the program will *execute* (run) the function by asking me for a number, then *returning* it (giving it back to me) by saving it inside the variable `age`. Now when I want to ask the user for another number (this time representing the school year), I do the same thing with the variable `school_year`. 

###  Reusable functions

This is all well and good, but I can make my function do much more for me. Right now, my function will always ask the user for a number by printing the string `"Give me a number: "`. What if I want to print a different string every time I ask the user for a number, but otherwise use the same idea for the function? In other words, I want a variable parameter in my function that changes every time I call the function based on something I (the programmer) want to be different. 

I can do this by *passing* (giving) my function a variable. Like this: 

{% highlight python %}
  def get_integer(help_text):
    return int(input(help_text))
{% endhighlight %}

Now what I can do when I call the function is something like this: 

{% highlight python %}
  def get_integer(help_text):
    return int(input(help_text))

  age = get_integer("Tell me your age: ")
  school_year = get_integer("What grade are you in? ")
  if age > 15:
    print("You are over the age of 15")
  print("You are in grade " + str(school_year))
{% endhighlight %}

Now it is easier for a user to use the program, because the help text is different. 

These variables you pass to functions are called *variables*, *parameters*, or *arguments*.

### Default arguments

In the example above, once I have added an *argument* to my function, I always have to give an argument when I call the function. I can't forget to give the `get_integer()` function from above a string to print to the screen. In some cases, I want there to be a "default" behavior for my function that happens when I create an argument for it but don't give it any. 

In the example above, if I don't give a custom string (which may be 95% of the time I use this function), I just want the `input()` line to say `"Give me a number: "` and I want to save myself the trouble of writing this every single time I call the function. So what I can do is give my function *default arguments*. Like so: 

{% highlight python %}
  def get_integer(help_text="Give me a number: "):
    return int(input(help_text))
{% endhighlight %}

What happens now is I can use the function in two ways: by giving it an argument and by NOT giving it an argument. 

{% highlight python %}
  def get_integer(help_text):
    return int(input(help_text))

  age = get_integer("Tell me your age: ")
  school_year = get_integer()
  if age > 15:
    print("You are over the age of 15")
  print("You are in grade " + str(school_year))
{% endhighlight %}

The first time I call the function, it will print `"Tell me your age: "`, but the second time, it will print `"Give me a number: "`, because I did not give it a string and it will execute the default behavior.

### Recap

What a function does is wrap a piece of code that we want to reuse, labels it, and allows us to use it again relatively easily. You can add variables to the functions to make your code even MORE reusable, and you can add default arguments to these variables.

Functions are a bit strange to deal with at first, but once you master them, they will be your savior in programming. Besides, the whole point of learning programming is abstraction, problem solving, breaking down problems, and that's exactly what functions are all about.

{% include submit.md %}