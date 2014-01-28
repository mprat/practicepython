## Exercise

Ask the user for a string and print out whether this string is a palindrome or not. (A **palindrome** is a string that reads the same forwards and backwards.)

## Discussion

Concepts for this week: 

* Strings are lists

### Strings are lists

Because strings are lists, you can do to strings everything that you do to lists. You can iterate through them: 

```
string = "example"
for c in string: 
	print "one letter: " + c
```

Will give the result:

```
one letter: e
one letter: x
one letter: a
one letter: m
one letter: p
one letter: l
one letter: e
```

You can take sublists: 

```
string = "example"
s = string[0:5]
print s
```

Now `s` has the string "exam" in it. 

Moral of the story: a string is a list.