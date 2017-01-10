---
layout: post
number: 26
chili: 2
categories: [exercise]
published: True
---

## Exercise {{ page.number }} (and [Solution]({{ site.baseurl }}{% post_url 2015-11-23-26-check-tic-tac-toe-solutions %}))

_This exercise is Part 2 of 4 of the Tic Tac Toe exercise series. The other 3 exercises are: [Part 1]({{ site.baseurl }}{% post_url 2014-12-27-24-draw-a-game-board %}), [Part 3]({{ site.baseurl }}{% post_url 2015-11-26-27-tic-tac-toe-draw %}), and [Part 4]({{ site.baseurl }}{% post_url 2016-08-03-29-tic-tac-toe-game %})._

In a [previous exercise]({{ site.baseurl }}{% post_url 2014-12-27-24-draw-a-game-board %}) we drew a Tic Tac Toe board. As you may have guessed, we are trying to build up to a full tic-tac-toe board. However, this is significantly more than half an hour of coding, so we're doing it in pieces.

Today, we will simply focus on checking whether someone has WON a game of Tic Tac Toe, not worrying about how the moves were made.

If a game of Tic Tac Toe is represented as a list of lists, like so:

{% highlight python %}
game = [[1, 2, 0],
	[2, 1, 0],
	[2, 1, 1]]
{% endhighlight %}

where a `0` means an empty square, a `1` means that player 1 put their token in that space, and a `2` means that player 2 put their token in that space.

Your task this week: given a 3 by 3 list of lists that represents a Tic Tac Toe game board, tell me whether anyone has won, and tell me which player won, if any. A Tic Tac Toe win is 3 in a row - either in a row, a column, or a diagonal. Don't worry about the case where TWO people have won - assume that in every board there will only be one winner.

Here are some more examples to work with: 

{% highlight python %}
winner_is_2 = [[2, 2, 0],
	[2, 1, 0],
	[2, 1, 1]]

winner_is_1 = [[1, 2, 0],
	[2, 1, 0],
	[2, 1, 1]]

winner_is_also_1 = [[0, 1, 0],
	[2, 1, 0],
	[2, 1, 1]]

no_winner = [[1, 2, 0],
	[2, 1, 0],
	[2, 1, 2]]

also_no_winner = [[1, 2, 0],
	[2, 1, 0],
	[2, 1, 0]]
{% endhighlight %}

## Topics

This exercise is challenging, but doable with only lists (of lists)! Lists of lists are nearly the same as lists, just a bit trickier. Remember that to get the first element in a list called `my_list = [5, 10, 15]`, you index it with a variable like so: 

{% highlight python %}
	>>> print(my_list[0])
	5
	>>> print(my_list[-1])
	15
	>>> print(len(my_list))
	3
{% endhighlight %}

When working with lists of lists, it is the same! Say you have a list `matrix = [[1, 2], [3, 4]]`. Then, take a look at this: 

{% highlight python %}
	>>> print(matrix[0])
	[1, 2]
	>>> print(matrix[-1])
	[3, 4]
	>>> first_row = matrix[0]
	>>> print(first_row[0])
	1
	>>> print(matrix[0][0])
	1
	>>> print(matrix[1][1])
	4
{% endhighlight %}

The cool part is that you can use double-indexing to read the elements from our list of lists `matrix`! By indexing `matrix[0][1]` we are saying give me the 1st element of the 0th element of `matrix`, which in this case is `2`.

Happy Coding!

{% include submit.md %}