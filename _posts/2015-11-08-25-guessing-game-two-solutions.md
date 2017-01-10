---
layout: post
number: 25
categories: [solution]
published: True
---

## [Exercise {{ page.number }}]({{ site.baseurl }}{% post_url 2015-11-01-25-guessing-game-two %})

In [a previous exercise]({{ site.baseurl }}{% post_url 2014-04-02-09-guessing-game-one %}), we've written a program that "knows" a number and asks a user to guess it.

This time, we're going to do exactly the opposite. You, the user, will have in your head a number between 0 and 100. The program will guess a number, and you, the user, will say whether it is too high, too low, or your number. 

At the end of this exchange, your program should print out how many guesses it took to get your number.

As the writer of this program, you will have to choose how your program will strategically guess. A naive strategy can be to simply start the guessing at 1, and keep going (2, 3, 4, etc.) until you hit the number. But that's not an optimal guessing strategy. An alternate strategy might be to guess 50 (right in the middle of the range), and then increase / decrease by 1 as needed. After you've written the program, try to find the optimal strategy! (We'll talk about what is the optimal one next week with the solution.)


## Sample solution

One user implemented an interesting strategy. Based on whether the number was lower or higher than the guess, randomly pick a number in that direction. This code is easy to read, even if it does not achieve the most efficient solution (and depends a little bit on randomness).

<script src="https://gist.github.com/anonymous/4da27a975ad14d590a84.js"></script>

Here is one user solution, implementing binary search: 

<script src="https://gist.github.com/anonymous/97e6b3f876d3b257f5cc.js"></script>

## Explanation

## Theory

The problem given in this exercise is called a search problem - the objective is to find something. It is solved by an algorithm called a search algorithm - an algorithm designed to find something. Not rocket science, I know, just terminology.

The most optimal solution to this problem requires an algorithm called [binary search](https://en.wikipedia.org/wiki/Binary_search_algorithm), the most efficient search algorithm on sorted lists (for those who know about computational complexity, binary search is an `O(log n)` algorithm).

In a nutshell, binary search picks an element from a sorted list, then decides (based on some feedback of the target), whether to look earlier or later in the list. In the optimal form, the binary search algorithm will always look at the "center" of the list in question. The catch is that binary search relies on having the original list in question be _sorted_, or ordered either smallest to largest or largest to smallest.


### Example + Code

Let's go through an example. Say you have this list: `my_list = [-10, 1, 2, 6, 7, 12, 21]`, and we are trying to find the element `12` in the smallest number of steps. This means we want to search through the list until we find `8`, and keep track of the index we look at. The binary search algorithm will start by looking at the item in the middle (in this case `6`). We then task, is `6` less than or greater than our target (`12`)? It is less, so we need to look at the RIGHT HALF of the list. This means our new list we are looking at is `[7, 12, 21]`. We again look at the "center" element (`12`), and compare. It is `12`, our target, so we are done! 

In code, we can accomplish this with a `while` loop. We want to keep going until either we haven't found the element, or our guess is equal to the element. The end conditions are `len(my_list) == 0` or `guess == target`, so the `while` loop continues while those two conditions are NOT met. 

The function will look something like this (in Python 3), assuming the list is sorted from smallest to largest:  

{% highlight python %}
my_list = [-10, 1, 2, 6, 7, 12, 21]
target = 12
guess = 0
while not (len(my_list) == 1 or guess == target):
  center_index = int(len(my_list) / 2)
  guess = my_list[center_index]
  if guess > target:
    my_list = my_list[:center_index]
  elif guess < target:
    my_list = my_list[center_index:]

if guess == target:
  print("Found target! Guess = " + str(guess))
else:
  print("Target not found. Last guess = " + str(guess))
{% endhighlight %}

A few tricky things to note from the code: 

* We want to always be looking at the "center" element of the list, but if the list (or sublist) has an even number of elements, it needs to be converted into an integer, so it can be used as an index into a list. In my case, I just converted the result of the length of the list divided by 2 into an int, but there are other ways.
* The variable `guess` has to be given a value to start, but it doesn't matter what that value is as long as it is not equal to `target`. (_Why? because if `guess` were to start out equal to `target`, the loop will never happen._)
* I have two conditions in my `if` statement: if the `guess` is less than the `target`, or if `guess` is greater than the `target`. In the case of the `guess` being less than the `target`, I want to look at the half of the list on the RIGHT side of the `guess`. The way I wrote it here, I am including the `guess` element in the sublist - this is not hugely important, since we will most likely remove that element later in the process anyway.
* You can put a `print(my_list)` and/or a `print(guess)` inside the `while` loop after the `if` statement to see the progress of the code.

### Bonus code

Lets way we wanted to add "monitoring" to our code. How many times did the `while` loop execute? Let's just add a counter!


{% highlight python %}
my_list = [-10, 1, 2, 6, 7, 12, 21]
target = 12
guess = 0
numbet_of_loops = 0
while not (len(my_list) == 1 or guess == target):
  center_index = int(len(my_list) / 2)
  guess = my_list[center_index]
  if guess > target:
    my_list = my_list[:center_index]
  elif guess < target:
    my_list = my_list[center_index:]
  number_of_loops += 1

if guess == target:
  print("Found target! Guess = " + str(guess))
else:
  print("Target not found. Last guess = " + str(guess))
print("while loop executed " + str(number_of_loops) + " times")
{% endhighlight %}

Try changing the value of `target` and see what happens!

If you are feeling excited about this code and want to play more, try this bonus challenge: what happens if the list is sorted from largest to smallest? What has to change in the code?

### Answering the original question

So, to answer the original question, there are two things that need to be modified from our code snippet above: 

1. The target needs to be set. The problem specifically specifies asking the user for feedback about whether the number is too big or too small, so that needs to be incorporated into the `while` loop. 
2. The list is now not a random collection of numbers - it is all the numbers in `range(0, 100)`, so you can either construct the list that way, or compute the guesses on the fly without the list (like in the sample solution above).

There are many ways to solve this problem! Try a few of them and see what you like.

## Further reading

* [Wikipedia article on binary search](https://en.wikipedia.org/wiki/Binary_search_algorithm)
* [Khan academy lecture on binary search](https://www.khanacademy.org/computing/computer-science/algorithms/binary-search/a/implementing-binary-search-of-an-array)


Happy hacking!