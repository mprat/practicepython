---
layout: post
number: 8
tags: [exercise]
---

## Exercise

Make a two-player Rock-Paper-Scissors game. (_Hint: Ask for player plays (using `input`), compare them, print out a message of congratulations to the winner, and ask if the players want to start a new game_)

Remember the rules: 

* Rock beats scissors
* Scissors beats paper
* Paper beats rock

## Discussion

Concepts for this week:

* While loops
* Infinite loops
* Break statements

### While loops

We have already discussed `for` loops, or loops that look sequentially (one by one) at elements in a list. There is a second type of loop that works in a slightly different way called a `while` loop. 

The idea is simple: while a certain condition is `True`, keep doing something. For example: 

{% highlight python %}
  a = 5
  while (a > 0):
    print(a)
    a -= 1
{% endhighlight %}

The output of this code segment is: 

{% highlight python %}
  5
  4
  3
  2
  1
{% endhighlight %}

A particularly useful way to use `while` loops is checking user input for correctness. For example: 

{% highlight python %}
  quit = input('Type "enter" to quit:' )
  while quit != "enter":
    quit = input('Type "enter" to quit:' )
{% endhighlight %}

The uses for this are infinite, and can (and should!) be combined with conditionals to yield the most efficient results. 

### Infinite loops

An infinite loop is a loop that never stops. This means that the condition in the beginning of the while loop will always be true. 

For example: 

{% highlight python %}
  i = 5
  while i > 0:
    print("Inside the loop")
{% endhighlight %} 

What will happen is the loop will print out the phrase "Inside the loop" forever and ever. If you are running your computer, you will have to "kill the program" to stop it. Each operating system has a different way of "killing a program" to get out of an infinite loop. 

On Linux: in the terminal, type "CTRL-D" to kill the program that is currently running in the terminal. 

On Windows: type "CTRL-ALT-DEL" and open the task manager to kill the program. 

On Mac: right-click on the task, and kill the program that is running forever.

If you find yourself in an infinite loop, your program will never end.

### Break statements

A `break` statement stops the execution of a loop before the original condition is met. While the use of a `break` statement will often start an argument about good coding practices, sometimes it is useful. 

For example: 

{% highlight python %}
  while True: 
    usr_command = input("Enter your command: ")
    if usr_command == "quit":
      break
    else: 
      print("You typed " + usr_command)
{% endhighlight %}

In this case, the `break` statement is used to break off the "infinite while loop" that we have constructed with the `while True` statement.

{% include submit.md %}