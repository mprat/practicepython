---
layout: post
number: 37
categories: [solution]
---

This exercise asked you to refactor this code snippet to refactor (taken from a correct but very repeated solution to [exercise 24]({% post_url 2014-12-27-24-draw-a-game-board %}) on this website):

{% highlight python %}
print(" --- --- ---")
print("|   |   |   |")
print(" --- --- ---")
print("|   |   |   |")
print(" --- --- ---")
print("|   |   |   |")
print(" --- --- ---")
{% endhighlight %}

_Hint: Think about a way to refactor this using functions where generating an 8x8 or a 19x19 grid is a single change to a function call!_

## Solution

What we can see right away is the repeated structure of the vertical and horizontal lines. Our strategy therefore is going to be to write one function for the vertical lines, and one function for the horizontal lines.

{% highlight python %}
def print_verticals(grid_size):
	vertical_string = "|"
	for i in range(grid_size):
		vertical_string += "   |"
	print(vertical_string)

def print_horizontals(grid_size):
	horiz_string = ""
	for i in range(grid_size):
		horiz_string += " ---"
	print(horiz_string)
{% endhighlight %}

This way, with these two functions, we can print the grid in a repeatable way for a square grid, just by changing a single variable (`grid_size`):

{% highlight python %}
grid_size = 3
print_horizontals(grid_size)
for i in range(grid_size):
	print_verticals(grid_size)
	print_horizontals(grid_size)
{% endhighlight %}

The cool part about this function split is that to make an asymmetrical grid, we instead use two variables `grid_size_x` and `grid_size_y` to control how many squares in the `x` and `y` direction we want, without having to change any of our printing code:

{% highlight python %}
grid_size_x = 3
grid_size_y = 5
print_horizontals(grid_size_x)
for i in range(grid_size_y):
	print_verticals(grid_size_x)
	print_horizontals(grid_size_x)
{% endhighlight %}

prints out:

```
 --- --- ---
|   |   |   |
 --- --- ---
|   |   |   |
 --- --- ---
|   |   |   |
 --- --- ---
|   |   |   |
 --- --- ---
|   |   |   |
 --- --- ---
```

Happy coding!