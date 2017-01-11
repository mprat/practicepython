---
layout: post
number: 1
chili: 1
categories: [exercise]
tags: [input, strings, types, int]
light_text: printing basic strings
---

Calibrating the exercises to the audience is going to be a challenging task, so I ask you to bear with me if the exercises are too easy or too hard. Every week there will be a poll you can click on to discuss whether the exercise is too easy or too hard and hopefully in a few weeks, I'll get the level right. Let's get to it! I will start with the exercise and include a discussion later, in case you want the extra challenge.

{% include exercise_header.md number=page.number %}

Create a program that asks the user to enter their name and their age. Print out a message addressed to them that tells them the year that they will turn 100 years old. 

Extras: 

1. Add on to the previous program by asking the user for another number and printing out that many copies of the previous message. (_Hint: [order of operations](http://www.mathsisfun.com/operation-order-pemdas.html) exists in Python_)
2. Print out that many copies of the previous message on separate lines. (_Hint: the string `"\n` is the same as pressing the ENTER button_)

## Discussion

Concepts for this week:

* Getting user input 
* Manipulating strings (a few ways)

### User input in Python

To get user input in Python (3), the command you use is [`input()`](http://docs.python.org/3.3/library/functions.html?highlight=input#input). Store the result in a variable, and use it to your heart's content. Remember that the result you get from the user will be a string, even if they enter a number. 

For example, 

{% highlight python %}
name = input("Give me your name: ")
print("Your name is " + name)
{% endhighlight %}

What this will print in the terminal (or the shell, whatever you are running Python in) will be: 

{% highlight python %}
>>> Give me your name: Michele
Your name is Michele
{% endhighlight %}

What happens at the end of `input()` is that it waits for the user to type something and press ENTER. Only after the user presses ENTER does the program continue.
 
### Manipulating strings (a few ways)

What you get from the `input()` function is a string. What can you do with it? 

First: Make the string into a number. Let's say you are 100% positive that the user entered a number. You can turn the string into an integer with the function [`int()`](http://docs.python.org/3.3/library/functions.html#int). (In a later exercise or two or three there will be questions about what to do when the user does NOT enter a number and you try to do this; for now don't worry about that problem). Here is what this looks like: 

{% highlight python %}
age = input("Enter your age: ")
age = int(age)
{% endhighlight %}

(or, if you want to be more compact with your code)

{% highlight python %}
age = int(input("Enter your age: "))
	
{% endhighlight %}
		
In both cases, `age` will hold a variable that is an integer, and now you can do math with it. 

(Note, you can also turn integers into strings exactly in the opposite way,
using the [`str()`](http://docs.python.org/3.3/library/functions.html#str) function) 

Second: Do math with strings. What do I mean by that? I mean, if I want to combine (**concatenate** is the computer science word for this) strings, all I need to do is add them: 

{% highlight python %}
	
print("Were" + "wolf")
print("Door" + "man")
print("4" + "chan")
print(str(4) + "chan")
{% endhighlight %}

The same works for multiplication:

{% highlight python %}

print(4 * "test")
{% endhighlight %}

 but division and subtraction do not work like this. In terms of multiplication, the idea of multiplyling two strings together is not well-defined. What does it mean to multiply two strings in the first place? However, it makes sense in a way to specify multiplying a string by a number - just repeat that string that number of times. Try this in your own program with all the arithmetic operations with numbers and strings - the best way to get a feel for what works and what doesn't is to try it!

{% include submit.md %}
