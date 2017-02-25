---
layout: post
number: 33
chili: 1
part: 2
of: 4
part_text: birthday data
categories: [solution]
---

{% include solution_header.md number=post.number %}

{% include parts_sentence.md part=page.part part_text=page.part_text part_of=page.of %}

In the [previous exercise]({{ site.baseurl }}{% post_url 2017-01-24-33-birthday-dictionaries %}) we created a dictionary of famous scientists' birthdays. In this exercise, modify your program from [Part 1]({{ site.baseurl }}{% post_url 2017-01-24-33-birthday-dictionaries %}) to load the birthday dictionary from a JSON file on disk, rather than having the dictionary defined in the program.

**Bonus**: Ask the user for another scientist's name and birthday to add to the dictionary, and update the JSON file you have on disk with the scientist's name. If you run the program multiple times and keep adding new names, your JSON file should keep getting bigger and bigger.

## Sample solution


