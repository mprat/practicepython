---
layout: post
categories: [exercise]
number: 37
chili: 2
---

One area of confusion for new coders is the concept of functions (which have been addressed on this blog in [exercise 11]({% post_url 2014-04-16-11-check-primality-functions %}) for example). So in this exercise, we will be stretching our functions muscle by _refactoring_ an existing code snippet into using functions.

Here is the code snippet to refactor (taken from a correct but very repeated solution to [exercise 24]({% post_url 2014-12-27-24-draw-a-game-board %}) on this website):

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

## Discussion

Oftentimes as we write a program, we find ourselves wanting to reuse the same piece of code over and over again. This is a great use case for a function, and in particular, re-writing a piece of code (known as _refactoring_) to use a function. We often refactor code to use a function or functions to not repeat similar code segments, and make the code less error-prone.

As an example of how to do this, let's take the following code snippet for playing the [Rock, Paper, Scissors game from exercise 8]({% post_url 2014-03-26-08-rock-paper-scissors %}) and refactor.

The following snippet is a complete piece of code for playing the game Rock Paper Scissors.

{% highlight python %}
while True:
	player1 = ""
	while player1 not in ["rock", "paper", "scissors"]:
		player1 = input("player1 make your move (rock, paper, scissors): ")
	player2 = ""
	while player2 not in ["rock", "paper", "scissors"]:
		player2 = input("player2 make your move (rock, paper, scissors): ")
	winner_message = ""
	if player1 == player2:
		winner_message = "The outcome is a tie"
	elif player1 == "rock" and player2 == "scissors":
		winner_message = "player1 is the winner"
	elif player1 == "paper" and player2 == "rock":
		winner_message = "player1 is the winner"
	elif player1 == "scissors" and player2 == "paper":
		winner_message = "player1 is the winner"
	elif player2 == "rock" and player1 == "scissors":
		winner_message = "player2 is the winner"
	elif player2 == "paper" and player1 == "rock":
		winner_message = "player2 is the winner"
	elif player2 == "scissors" and player1 == "paper":
		winner_message = "player2 is the winner"
	print(winner_message)
	again = ""
	while again not in ["y", "n"]:
		again = input("Do you want to play again? (y/n): ")
	if again == "n":
		break
{% endhighlight %}

When looking at this piece of code, we see two things that stand out as "repeated blocks":

1. Asking for player 1's input and asking for player 2's input is an identical piece of code
2. The `if`/`else` checking for who is the winner has many doubled checks

So let's use these two as inspiration for refactoring. First, getting input from either player - let's put that code into a separate function:

{% highlight python %}
def get_move():
    move = ""
    while move not in ["rock", "paper", "scissors"]:
    	move = input("player2 make your move (rock, paper, scissors): ")
    return move
{% endhighlight %}

Now we can use this function in our new gameplay for Rock Paper Scissors:

{% highlight python %}
def get_move():
    move = ""
    while move not in ["rock", "paper", "scissors"]:
    	move = input("player2 make your move (rock, paper, scissors): ")
    return move

while True:
	player1 = get_move()
	player2 = get_move()
	winner_message = ""
	if player1 == player2:
		winner_message = "The outcome is a tie"
	elif player1 == "rock" and player2 == "scissors":
		winner_message = "player1 is the winner"
	elif player1 == "paper" and player2 == "rock":
		winner_message = "player1 is the winner"
	elif player1 == "scissors" and player2 == "paper":
		winner_message = "player1 is the winner"
	elif player2 == "rock" and player1 == "scissors":
		winner_message = "player2 is the winner"
	elif player2 == "paper" and player1 == "rock":
		winner_message = "player2 is the winner"
	elif player2 == "scissors" and player1 == "paper":
		winner_message = "player2 is the winner"
	print(winner_message)
	again = ""
	while again not in ["y", "n"]:
		again = input("Do you want to play again? (y/n): ")
	if again == "n":
		break
{% endhighlight %}

When looking at the big `while True` loop we can see two calls of the function `get_move()`, which makes it clear what we are doing for each player's move.

Now let's tackle the winner-checking as a function. This is a bit more subtle for how to refactor. One thing we notice from the existing code is that we have two sets of conditions: one to check whether player 1 is the winner, and one to check whether player 2 is the winner. However, this code is duplicated. Instead, what we will do is write a function that will return "is the first player the winner" and call that function twice.

{% highlight python %}
def is_first_the_winner(first, second):
	if first == "rock" and second == "scissors" or \
			first == "paper" and second == "rock" or \
			first == "scissors" and second == "paper": 
		return True
	return False
{% endhighlight %}

Now we refactor our main code with this helper function:

{% highlight python %}
def get_move():
    move = ""
    while move not in ["rock", "paper", "scissors"]:
    	move = input("player2 make your move (rock, paper, scissors): ")
    return move

def is_first_the_winner(first, second):
	if first == "rock" and second == "scissors" or \
			first == "paper" and second == "rock" or \
			first == "scissors" and second == "paper": 
		return True
	return False

while True:
	player1 = get_move()
	player2 = get_move()
	winner_message = ""
	if player1 == player2:
		winner_message = "The outcome is a tie"
	elif is_first_the_winner(player1, player2):
		winner_message = "player1 is the winner"
	elif is_first_the_winner(player2, player1):
		winner_message = "player2 is the winner"
	print(winner_message)
	again = ""
	while again not in ["y", "n"]:
		again = input("Do you want to play again? (y/n): ")
	if again == "n":
		break
{% endhighlight %}

Now what we have is an easy-to-read program with two functions that don't have any repeated code! Happy coding.