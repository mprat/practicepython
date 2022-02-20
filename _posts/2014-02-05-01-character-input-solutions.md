---
layout: post
number: 1
categories: [solution]
---

Because I cannot include every single submission I get, I will choose one or two that are example answers and include those within each post. 

Create a program that asks the user to enter their name and their age. Print out a message addressed to them that tells them the year that they will turn 100 years old. 

## Solution

{% highlight python %}
name = input("What is your name: ")
age = int(input("How old are you: "))
year = 2014 - age + 100
print(name + ", you will be 100 years old in the year " + str(year))
{% endhighlight %}
