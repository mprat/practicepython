Exercise

Let's say you have a text-based 3x3 game board that looks like this: 

{% highlight python %}
 --- --- --- 
|   |   |   | 
 --- --- ---  
|   |   |   | 
 --- --- ---  
|   |   |   | 
 --- --- --- 
{% endhighlight %}

(Yep, like a tic tac toe board. Take a look at the [exercise](SOMETHING) and [solution](SOMETHING) for how to draw this board to the screen in Python 3.)

I want to be able to keep track (and re-draw) the game board every time someone makes a move. In this exercise, let's keep it simple - we won't deal with mouse clicks or other complex user input. 

All you need to do is ask the user for a coordinate (like (1,1), (3,3), etc.), and re-draw the board with an "x" in that particular square. 

For example, my program will draw the board to the screen: 

 -- -- --
|  |  |  |
 -- -- -- 
|  |  |  |
 -- -- -- 
|  |  |  |
 -- -- --

  