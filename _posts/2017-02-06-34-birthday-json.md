---
layout: post
number: 34
chili: 2
part: 2
of: 4
categories: [exercise]
part_text: birthday data
---

{% include parts_sentence.md part=page.part part_text=page.part_text part_of=page.of %} 

In the [previous exercise]({{ site.baseurl }}{% post_url 2017-01-24-33-birthday-dictionaries %}) we created a dictionary of famous scientists' birthdays. In this exercise, modify your program from [Part 1]({{ site.baseurl }}{% post_url 2017-01-24-33-birthday-dictionaries %}) to load the birthday dictionary from a JSON file on disk, rather than having the dictionary defined in the program.

**Bonus**: Ask the user for another scientist's name and birthday to add to the dictionary, and update the JSON file you have on disk with the scientist's name. If you run the program multiple times and keep adding new names, your JSON file should keep getting bigger and bigger.

## Discussion

In a previous exercise we talked about [how to save information to a .txt file on disk]({{ site.baseurl }}{% post_url 2014-11-30-21-write-to-a-file %}), but in this exercise we are talking about writing a different kind of file format called JSON.

The JSON file format was developed in the early 2000s as a standard for how web servers would pass data back and forth. It is still used for web server communication today, and it conveniently is also a way we can store dictionary-like data in a file on disk. The JSON format specifies a way to _serialize_ (turn into a string) a dictionary or list, which then means that string can be written to disk or passed to another application. JSON is meant to store dictionary-like data both in a readable way for humans, and in a compact way that can be read by computers. Because it is a standard format, you can write JSON in one language and read JSON from another language to effectively pass information between the two programs or applications. You can read more about the history of JSON on [the wikipedia article](https://en.wikipedia.org/wiki/JSON).

Here is an example of JSON:

{% highlight json %}
{
    "name": "Michele",
    "shirt_color": "blue",
    "laptops": [
    {
        "brand": "Lenovo",
        "operating_system": "Ubuntu"
    },
    {
        "brand": "Apple",
        "operating_system": "OSX"
    }
    ],
    "has_a_dog": false,
    "items_on_desk": ["mug", "pen", "monitor"]
}
{% endhighlight %}

Notice how you can mix dictionaries and lists. In this example the top-level container is a dictionary, with the keys `name`, `shirt_color`, `laptops`, `has_a_dog`, and `items_on_desk`. The keys can be lists, strings, booleans, or other dictionaries. Usually you don't write JSON by hand (but it is very readable so you easily could). One of my favorite tools to test whether you've written valid JSON is this free [JSON validator](http://jsonlint.com/) - just paste your JSON in there and it tells you if it will be read by a program that understands JSON.

There is a built-in Python library for reading and writing JSON files, so you don't have to worry about how your dictionaries and lists are going to be turned into the right format!

As long as the data you want to store is either a dictionary or a list of dictionaries, writing JSON is straightforward. First, import the [`json` library](https://docs.python.org/3/library/json.html) (no installation needed, it is built in to Python) and initialize some dictionary:

{% highlight python %}
import json

info_about_me = {
    "name": "Michele",
    "has_a_dog": False
}
{% endhighlight %}

Then, to save your dictionary to disk you need to open a file and use the `json.dump()` method. Remember to use the `w` flag when opening a file for writing:

{% highlight python %}
with open("info.json", "w") as f:
    json.dump(info_about_me, f)
{% endhighlight %}

And you will have saved a file called `info.json` in the same directory as your Python program. The dictionary `info_about_me` will be saved to disk, but the variable name will not be. Basically, JSON won't remember the name of the variable you saved your dictionary in. If you open the file with a text editor (Notepad++, vim, emacs, Sublime Text, etc.), you will just see:

{% highlight json %}
{
    "name": "Michele",
    "has_a_dog": false
}
{% endhighlight %}

Alternatively, you can also manually create a JSON file and type JSON directly into it (passing it through [the JSON validator](http://jsonlint.com/) of course!). Just save the file with the `.json` extension and copy the dictionary directly into the file.

Now I can use the information about me that I saved to disk in another program (written in a completely different file) to do something like printing a message. When I saved the JSON file, the variable name of my dictionary was not saved with it, so when I load the JSON file I need to save it into a variable. I can use the same `json` library to do this:

{% highlight python %}
import json

with open("info.json", "r") as f:
    info = json.load(f)

if info["has_a_dog"]:
    print("{} has a dog".format(info["name"]))
else:
    print("{} does not have a dog".format(info["name"]))
{% endhighlight %}

When this program runs, the output should be:

{% highlight text %}
Michele does not have a dog
{% endhighlight %}

Notice how when I loaded the JSON file I used a different name than when I saved it - this is because the variable names don't get saved together with the JSON data, so you do not have to use the same variable names to save and load JSON.

Now that you know about JSON, you can use it to do a number of things:

* Save data to disk that can be shared by people and programs.
* Constantly update data that needs to be shared by re-saving and re-load to disk.
* Save data from a program that a human can read and manually check and fix errors.

{% include submit.md %}