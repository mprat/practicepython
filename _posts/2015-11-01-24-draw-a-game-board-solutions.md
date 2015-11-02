---
layout: post
number: 24
categories: [solution]
published: True
---

## [Exercise]({{ site.baseurl }}{% post_url 2014-12-27-24-draw-a-game-board %})


Time for some fake graphics! Let's say we want to draw game boards that look like this: 

{% highlight python %}
 --- --- --- 
|   |   |   | 
 --- --- ---  
|   |   |   | 
 --- --- ---  
|   |   |   | 
 --- --- --- 
{% endhighlight %}

This one is 3x3 (like in tic tac toe). Obviously, they come in many other sizes (8x8 for chess, 19x19 for Go, and many more).

Ask the user what size game board they want to draw, and draw it for them to the screen using Python's `print` statement. 

Remember that in Python 3, printing to the screen is accomplished by

{% highlight python %}
  print("Thing to show on screen")
{% endhighlight %}

_Hint: this requires some use of functions, as were discussed [previously on this blog]({{ site.baseurl }}{% post_url 2014-04-16-11-check-primality-functions %}) and [elsewhere on the Internet, like this TutorialsPoint link](http://www.tutorialspoint.com/python/python_functions.htm)._


## Sample solution

Let's break this task into pieces and use Python 3.

First, the user needs to a numbers that represent the size of the game board (assuming the game board will be n by n). (_Bonus exercise: extend the following code to make the game board not square._). The following snippet assumes that the person entered a number and doesn't do any kind of error checking - for now, that's OK.

{% highlight python %}
  board_size = int(input("What size of game board? "))
{% endhighlight %}

Then, we need to draw each row of the game board. Each row consists of horizontal pieces (`---`) and vertical pieces (`|`). Each of these shows up in a pattern, so we can rely on for loops to help with the rendering.

To print a single row, we want to do something like this:

{% highlight python %}
  print(" --- " * board_size)
{% endhighlight %}

To print the vertical parts of the row, we want something like this, because we don't care about trailing whitespace, and because we want one more vertical line than the size of the board: 

{% highlight python %}
  print("|   " * (board_size + 1))
{% endhighlight %}

For a board of size _board_size_ we want to print that many horizontal pieces and vertical pieces, plus an extra horizontal piece for the bottom. Let's use functions for this entire operation, since we might want to change the style on the game boards for later use. All together, the program will look like this: 

{% highlight python %}
  def print_horiz_line():
    print(" --- " * board_size)

  def print_vert_line():
    print("|   " * (board_size + 1))

  if __name__ == "__main__":
    board_size = int(input("What size of game board? "))

    for index in range(board_size):
      print_horiz_line()
      print_vert_line()
    print horiz_line()
{% endhighlight %}

This way, if we ever decide to change the design of the game board by making it bigger, it will be easy to do! All we need to do is change the `print_horiz_line()` and `print_vert_line()` functions, and we're all set!

## A few user solutions not using functions

This one is pretty simple, and it is specific to the 3x3 board above. There is no way to change the size. Additionally, writing out the `a` and `b` lists in the print statement are tedious and can be improved with a list comprehension or for loop.

{% gist 013666be7c968cb514ce %}

The author chose to use a `while` loop instead of a `for` loop to do the printing, which was an interesting choice. But it works!
{% gist bf21e160a74e16923664 %}


Happy hacking!