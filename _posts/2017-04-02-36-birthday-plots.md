---
layout: post
number: 36
chili: 3
part: 4
of: 4
part_text: birthday data
categories: [exercise]
bokeh: true
---

In the [previous exercise]({{ site.baseurl }}{% post_url 2017-02-28-35-birthday-months %}) we counted how many birthdays there are in each month in our dictionary of birthdays.

In this exercise, use the [bokeh](http://bokeh.pydata.org/en/latest/) Python library to plot a histogram of which months the scientists have birthdays in! Because it would take a long time for you to input the months of various scientists, you can use [my scientist birthday JSON file]({{ site.baseurl }}/assets/scientist_birthdays.json). Just parse out the months (if you don't know how, I suggest looking at the [previous exercise]({{ site.baseurl }}{% post_url 2017-02-28-35-birthday-months %}) or [its solution]({{ site.baseurl }}{% post_url 2017-03-19-35-birthday-months-solutions %})) and draw your histogram.

If you are using a purely web-based interface for coding, this exercise won't work for you, since it requires installing the `bokeh` Python package. Now might be a good time to [install Python on your own computer]({% post_url 2017-03-24-install-python %}).

# Discussion

Today's topic is going to be about the [bokeh](http://bokeh.pydata.org/en/latest/) plotting library. We create plots and charts to display and communicate information from data, and it would be great to do that directly from Python. Sometimes it is really nice to write code or algorithms from scratch to learn and practice, and sometimes, someone has already written the code so well that you should use theirs. Bokeh is one of these libraries - it is library specifically with functions for making plots, charts, and graphs. It is based on the famous [D3.js](https://d3js.org/) library originally developed at the _New York Times_ for their visualizations, which has been used for many years to programmatically create visually appealing data visualizations.

## When to make plots

We use plots to convey information. From this histogram:

![US Government spending histogram]({{ site.baseurl }}/assets/imgs/united-states-government-spending.png)

You can immediately see that the US government spending has been steadily increasing, reaching a peak in January 2017.

So learning how to make plots will help you become better at displaying and communicating information, both to yourself and to others.

## Plotting libraries in Python

If you are looking for a plotting library in Python, you have two main options: [matplotlib](http://matplotlib.org/) and [bokeh](http://bokeh.pydata.org/en/latest/). Today I want to discuss bokeh, because I think it will become more popular in years to come.

Many Python developers (and especially data scientists and researchers) will tell you that the most commonly used plotting library in Python is [matplotlib](http://matplotlib.org/). I myself was a matplotlib user for many years - the integrations with Python data libraries are great, and migrating from the MATLAB plotting environment to matplotlib is easy. But a friend introduced me to bokeh and I was hooked ever since. Because it is based on D3.js, the visualizations look smooth and professional.

There is no one "best" plotting library - you should use whichever one feels and looks better for you. But for the rest of this post, I'll talk about how to use bokeh to make a basic plot.

## Installing bokeh

To use bokeh, we first have to install it. Unlike something like [`json`](https://docs.python.org/3/library/json.html) or [`Counter`](https://docs.python.org/3/library/collections.html#collections.Counter) from previous exercises, bokeh does not come installed with Python.

If you are using the [Anaconda Python](https://www.continuum.io/downloads) distribution (which you should, if you are on Windows!) then you can install bokeh by typing 

{% highlight bash %}
conda install bokeh
{% endhighlight %}

in the Windows command prompt or the bash shell.

On OSX or GNU / Linux, just type

{% highlight bash %}
pip3 install bokeh
{% endhighlight %}

(If you have are using Python 2, you should do `pip install bokeh`.)

## Using bokeh

The basic idea of any plotting package is simple:

1. Load the data
2. Display the data

So the first thing you have to do is prepare some data. Usually, when you are plotting data you have two axes, or groups of data, an x-axis (or horizontal axis) and a y-axis (or vertical axis). The `x` variable is your input (independent) variable and the `y` variable is your output (dependent) variable.

For use in bokeh, your data should be loaded into two separate lists, one for the x-axis and one for the y-axis. The basic format of a bokeh (in this case histogram) looks like this:

{% highlight python %}
# need to import at least 3 things to make your
# bokeh plots work
from bokeh.plotting import figure, show, output_file

# we specify an HTML file where the output will go
output_file("plot.html")

# load our x and y data
x = [10, 20, 30]
y = [4, 5, 6]

# create a figure
p = figure()

# create a histogram
p.vbar(x=x, top=y, width=0.5)

# render (show) the plot
show(p)
{% endhighlight %}

The way bokeh outputs plots is really cool: when you run a piece of bokeh code, it outputs the result into an HTML file that you can then save and display in a web browser on it's own. After you run this segment on top, it will automatically open a web browser and show you a plot. 

One awesome feature of Bokeh is that it gives you a toolbar you can use to play with the graph - moving it around, zooming out, saving it, etc. Plus, you can put it directly into am HTML page!

It will look something like this:

<div class="bk-root" id="93fbfba1-3111-41d0-9061-f1167ce0c394" data-root-id="1621"></div>
            
<script type="application/json" id="1801">
  {"b71c6e00-8afb-4a00-8337-5c3d75677a83":{"defs":[],"roots":{"references":[{"attributes":{},"id":"1622","type":"DataRange1d"},{"attributes":{"coordinates":null,"formatter":{"id":"1664"},"group":null,"major_label_policy":{"id":"1665"},"ticker":{"id":"1631"}},"id":"1630","type":"LinearAxis"},{"attributes":{"coordinates":null,"group":null},"id":"1658","type":"Title"},{"attributes":{},"id":"1638","type":"PanTool"},{"attributes":{},"id":"1639","type":"WheelZoomTool"},{"attributes":{},"id":"1664","type":"BasicTickFormatter"},{"attributes":{"source":{"id":"1652"}},"id":"1657","type":"CDSView"},{"attributes":{"coordinates":null,"data_source":{"id":"1652"},"glyph":{"id":"1653"},"group":null,"hover_glyph":null,"muted_glyph":{"id":"1655"},"nonselection_glyph":{"id":"1654"},"view":{"id":"1657"}},"id":"1656","type":"GlyphRenderer"},{"attributes":{"axis":{"id":"1630"},"coordinates":null,"group":null,"ticker":null},"id":"1633","type":"Grid"},{"attributes":{},"id":"1667","type":"Selection"},{"attributes":{},"id":"1666","type":"UnionRenderers"},{"attributes":{"below":[{"id":"1630"}],"center":[{"id":"1633"},{"id":"1637"}],"left":[{"id":"1634"}],"renderers":[{"id":"1656"}],"title":{"id":"1658"},"toolbar":{"id":"1645"},"x_range":{"id":"1622"},"x_scale":{"id":"1626"},"y_range":{"id":"1624"},"y_scale":{"id":"1628"}},"id":"1621","subtype":"Figure","type":"Plot"},{"attributes":{},"id":"1631","type":"BasicTicker"},{"attributes":{"overlay":{"id":"1644"}},"id":"1640","type":"BoxZoomTool"},{"attributes":{},"id":"1635","type":"BasicTicker"},{"attributes":{},"id":"1642","type":"ResetTool"},{"attributes":{},"id":"1641","type":"SaveTool"},{"attributes":{},"id":"1643","type":"HelpTool"},{"attributes":{"fill_color":{"value":"#1f77b4"},"line_color":{"value":"#1f77b4"},"top":{"field":"top"},"width":{"value":0.5},"x":{"field":"x"}},"id":"1653","type":"VBar"},{"attributes":{},"id":"1624","type":"DataRange1d"},{"attributes":{"data":{"top":[4,5,6],"x":[10,20,30]},"selected":{"id":"1667"},"selection_policy":{"id":"1666"}},"id":"1652","type":"ColumnDataSource"},{"attributes":{},"id":"1628","type":"LinearScale"},{"attributes":{"tools":[{"id":"1638"},{"id":"1639"},{"id":"1640"},{"id":"1641"},{"id":"1642"},{"id":"1643"}]},"id":"1645","type":"Toolbar"},{"attributes":{"bottom_units":"screen","coordinates":null,"fill_alpha":0.5,"fill_color":"lightgrey","group":null,"left_units":"screen","level":"overlay","line_alpha":1.0,"line_color":"black","line_dash":[4,4],"line_width":2,"right_units":"screen","syncable":false,"top_units":"screen"},"id":"1644","type":"BoxAnnotation"},{"attributes":{"coordinates":null,"formatter":{"id":"1661"},"group":null,"major_label_policy":{"id":"1662"},"ticker":{"id":"1635"}},"id":"1634","type":"LinearAxis"},{"attributes":{},"id":"1665","type":"AllLabels"},{"attributes":{},"id":"1626","type":"LinearScale"},{"attributes":{},"id":"1662","type":"AllLabels"},{"attributes":{},"id":"1661","type":"BasicTickFormatter"},{"attributes":{"fill_alpha":{"value":0.2},"fill_color":{"value":"#1f77b4"},"hatch_alpha":{"value":0.2},"line_alpha":{"value":0.2},"line_color":{"value":"#1f77b4"},"top":{"field":"top"},"width":{"value":0.5},"x":{"field":"x"}},"id":"1655","type":"VBar"},{"attributes":{"axis":{"id":"1634"},"coordinates":null,"dimension":1,"group":null,"ticker":null},"id":"1637","type":"Grid"},{"attributes":{"fill_alpha":{"value":0.1},"fill_color":{"value":"#1f77b4"},"hatch_alpha":{"value":0.1},"line_alpha":{"value":0.1},"line_color":{"value":"#1f77b4"},"top":{"field":"top"},"width":{"value":0.5},"x":{"field":"x"}},"id":"1654","type":"VBar"}],"root_ids":["1621"]},"title":"Bokeh Application","version":"2.4.2"}}
</script>
<script type="text/javascript">
  (function() {
    const fn = function() {
      Bokeh.safely(function() {
        (function(root) {
          function embed_document(root) {
            
          const docs_json = document.getElementById('1801').textContent;
          const render_items = [{"docid":"b71c6e00-8afb-4a00-8337-5c3d75677a83","root_ids":["1621"],"roots":{"1621":"93fbfba1-3111-41d0-9061-f1167ce0c394"}}];
          root.Bokeh.embed.embed_items(docs_json, render_items);
        
          }
          if (root.Bokeh !== undefined) {
            embed_document(root);
          } else {
            let attempts = 0;
            const timer = setInterval(function(root) {
              if (root.Bokeh !== undefined) {
                clearInterval(timer);
                embed_document(root);
              } else {
                attempts++;
                if (attempts > 100) {
                  clearInterval(timer);
                  console.log("Bokeh: ERROR: Unable to run BokehJS code because BokehJS library is missing");
                }
              }
            }, 10, root)
          }
        })(window);
      });
    };
    if (document.readyState != "loading") fn();
    else document.addEventListener("DOMContentLoaded", fn);
  })();
</script>

The example above works when `x` is a numerical value. But, in the exercise, we are dealing with months, which is called a "categorical" variable (i.e. it belongs to a category, and is not continuous). To make sure bokeh draws the axis correctly, you need to specify a special call to `figure()` to pass an `x_range`, like so:

{% highlight python %}
from bokeh.plotting import figure, show, output_file

output_file("plot.html")
x_categories = ["a", "b", "c", "d", "e"]
x = ["a", "d", "e"]
y = [4, 5, 6]

p = figure(x_range=x_categories)
p.vbar(x=x, top=y, width=0.5)

show(p)
{% endhighlight %}

Here's what this one looks like:

<div class="bk-root" id="1cc70986-5765-4f3c-8dab-ebcc901298e2" data-root-id="1802"></div>
            
<script type="application/json" id="1981">
  {"883b6c59-c219-42d0-825d-9acf30299e7b":{"defs":[],"roots":{"references":[{"attributes":{"coordinates":null,"formatter":{"id":"1841"},"group":null,"major_label_policy":{"id":"1842"},"ticker":{"id":"1815"}},"id":"1814","type":"LinearAxis"},{"attributes":{"axis":{"id":"1814"},"coordinates":null,"dimension":1,"group":null,"ticker":null},"id":"1817","type":"Grid"},{"attributes":{"fill_alpha":{"value":0.1},"fill_color":{"value":"#1f77b4"},"hatch_alpha":{"value":0.1},"line_alpha":{"value":0.1},"line_color":{"value":"#1f77b4"},"top":{"field":"top"},"width":{"value":0.5},"x":{"field":"x"}},"id":"1834","type":"VBar"},{"attributes":{},"id":"1812","type":"CategoricalTicker"},{"attributes":{},"id":"1823","type":"HelpTool"},{"attributes":{},"id":"1819","type":"WheelZoomTool"},{"attributes":{},"id":"1818","type":"PanTool"},{"attributes":{},"id":"1809","type":"LinearScale"},{"attributes":{"bottom_units":"screen","coordinates":null,"fill_alpha":0.5,"fill_color":"lightgrey","group":null,"left_units":"screen","level":"overlay","line_alpha":1.0,"line_color":"black","line_dash":[4,4],"line_width":2,"right_units":"screen","syncable":false,"top_units":"screen"},"id":"1824","type":"BoxAnnotation"},{"attributes":{"source":{"id":"1832"}},"id":"1837","type":"CDSView"},{"attributes":{"coordinates":null,"data_source":{"id":"1832"},"glyph":{"id":"1833"},"group":null,"hover_glyph":null,"muted_glyph":{"id":"1835"},"nonselection_glyph":{"id":"1834"},"view":{"id":"1837"}},"id":"1836","type":"GlyphRenderer"},{"attributes":{"fill_alpha":{"value":0.2},"fill_color":{"value":"#1f77b4"},"hatch_alpha":{"value":0.2},"line_alpha":{"value":0.2},"line_color":{"value":"#1f77b4"},"top":{"field":"top"},"width":{"value":0.5},"x":{"field":"x"}},"id":"1835","type":"VBar"},{"attributes":{},"id":"1847","type":"Selection"},{"attributes":{"coordinates":null,"group":null},"id":"1838","type":"Title"},{"attributes":{"tools":[{"id":"1818"},{"id":"1819"},{"id":"1820"},{"id":"1821"},{"id":"1822"},{"id":"1823"}]},"id":"1825","type":"Toolbar"},{"attributes":{"overlay":{"id":"1824"}},"id":"1820","type":"BoxZoomTool"},{"attributes":{},"id":"1846","type":"UnionRenderers"},{"attributes":{"factors":["a","b","c","d","e"]},"id":"1803","type":"FactorRange"},{"attributes":{},"id":"1821","type":"SaveTool"},{"attributes":{},"id":"1815","type":"BasicTicker"},{"attributes":{},"id":"1845","type":"AllLabels"},{"attributes":{"below":[{"id":"1811"}],"center":[{"id":"1813"},{"id":"1817"}],"left":[{"id":"1814"}],"renderers":[{"id":"1836"}],"title":{"id":"1838"},"toolbar":{"id":"1825"},"x_range":{"id":"1803"},"x_scale":{"id":"1807"},"y_range":{"id":"1805"},"y_scale":{"id":"1809"}},"id":"1802","subtype":"Figure","type":"Plot"},{"attributes":{"coordinates":null,"formatter":{"id":"1844"},"group":null,"major_label_policy":{"id":"1845"},"ticker":{"id":"1812"}},"id":"1811","type":"CategoricalAxis"},{"attributes":{},"id":"1842","type":"AllLabels"},{"attributes":{},"id":"1844","type":"CategoricalTickFormatter"},{"attributes":{"data":{"top":[4,5,6],"x":["a","d","e"]},"selected":{"id":"1847"},"selection_policy":{"id":"1846"}},"id":"1832","type":"ColumnDataSource"},{"attributes":{"axis":{"id":"1811"},"coordinates":null,"group":null,"ticker":null},"id":"1813","type":"Grid"},{"attributes":{},"id":"1805","type":"DataRange1d"},{"attributes":{"fill_color":{"value":"#1f77b4"},"line_color":{"value":"#1f77b4"},"top":{"field":"top"},"width":{"value":0.5},"x":{"field":"x"}},"id":"1833","type":"VBar"},{"attributes":{},"id":"1822","type":"ResetTool"},{"attributes":{},"id":"1807","type":"CategoricalScale"},{"attributes":{},"id":"1841","type":"BasicTickFormatter"}],"root_ids":["1802"]},"title":"Bokeh Application","version":"2.4.2"}}
</script>
<script type="text/javascript">
  (function() {
    const fn = function() {
      Bokeh.safely(function() {
        (function(root) {
          function embed_document(root) {
            
          const docs_json = document.getElementById('1981').textContent;
          const render_items = [{"docid":"883b6c59-c219-42d0-825d-9acf30299e7b","root_ids":["1802"],"roots":{"1802":"1cc70986-5765-4f3c-8dab-ebcc901298e2"}}];
          root.Bokeh.embed.embed_items(docs_json, render_items);
        
          }
          if (root.Bokeh !== undefined) {
            embed_document(root);
          } else {
            let attempts = 0;
            const timer = setInterval(function(root) {
              if (root.Bokeh !== undefined) {
                clearInterval(timer);
                embed_document(root);
              } else {
                attempts++;
                if (attempts > 100) {
                  clearInterval(timer);
                  console.log("Bokeh: ERROR: Unable to run BokehJS code because BokehJS library is missing");
                }
              }
            }, 10, root)
          }
        })(window);
      });
    };
    if (document.readyState != "loading") fn();
    else document.addEventListener("DOMContentLoaded", fn);
  })();
</script>

There are also extra commands and arguments you can pass to bokeh to display an title for the plot, for each of the axis, for the color of the bars, and so on.

If you want to dive deep into that documentation, check out these resources:

* [Bar plots / histograms](http://bokeh.pydata.org/en/latest/docs/user_guide/plotting.html#bars)
* [Categorical axes](http://bokeh.pydata.org/en/latest/docs/user_guide/plotting.html#categorical-axes)
* [Everything to do with styling plots](http://bokeh.pydata.org/en/latest/docs/user_guide/styling.html)
* [Basic plotting for other types of graphs](http://bokeh.pydata.org/en/latest/docs/user_guide/plotting.html)

If you want to add more flair to your histogram from this exercise, there are many resources on the web to help you out!

Happy coding!
