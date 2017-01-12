---
layout: post
number: 34
chili: 1
part: 2
of: 4
categories: [exercise]
part_text: birthday data
---

{% include exercise_header.md number=page.number %}

{% include parts_sentence.md part=page.part part_text=page.part_text part_of=page.of %} 

In the [previous exercise]({{ site.baseurl }}{% post_url 2017-01-17-33-birthday-dictionaries %}) we created a dictionary of our friend's birthdays. This exercise will have you doing a bunch of steps to use JSON:

1. Take the original dictionary of friend's birthdays and save it to disk as JSON
2. Ask the user for another friend's name and birthday to add to the dictionary, and update the JSON file you have on disk. Save the name of the person your friend added.
3. Re-load the new dictionary from the file you saved, and check whether the added person was in the new dictionary.

## Discussion

In a previous exercise we talked about [how to save information to a .txt file on disk]({{ site.baseurl }}{% post_url 2014-11-30-21-write-to-a-file %}), but in this exercise we are talking about writing a different kind of file format.

after the dictionaries exercise, show how you can save information locally to disk by storing it to JSON. and how you can load it back into dictionaries and lists.
