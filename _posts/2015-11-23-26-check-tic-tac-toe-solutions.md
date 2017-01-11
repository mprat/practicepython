---
layout: post
number: 26
chili: 2
categories: [solution]
published: True
part: 2
of: 4
part_text: Tic Tac Toe
---

## Exercise {{ page.number }}

{% include parts_sentence.md part=page.part part_text=page.part_text part_of=page.of %}

As you may have guessed, we are trying to build up to a full tic-tac-toe board. However, this is significantly more than half an hour of coding, so we're doing it in pieces.

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

## Sample solutions

There were many strategies for approaching this problem. The important part is to be careful about checking rows, columns, and diagonals for winners. Things like making sure that a row of `0`, `0`, `0` doesn't win with player number 0 is important, and making sure to count the columns and rows at the edges.

A few submitted solutions are below - feel free to comment if you think you have a better one, and I'll put it up here!

Not using too many functions, but using the `numpy` library to transpose the game board, turning column-checking into row-checking.
<script src="https://gist.github.com/anonymous/b141c876ebc330bfeb13.js"></script>

Using `set()` to simplify the counting.
<script src="https://gist.github.com/CurveShot/e98159a400c325dc204f.js"></script>

Happy hacking!