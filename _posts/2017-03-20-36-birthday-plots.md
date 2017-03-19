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

{% include exercise_header.md number=page.number %}

{% include parts_sentence.md part=page.part part_text=page.part_text part_of=page.of %} 

In the [previous exercise]({{ site.baseurl }}{% post_url 2017-02-28-35-birthday-months %}) we counted how many birthdays there are in each month in our dictionary of birthdays.

In this exercise, use the [bokeh](http://bokeh.pydata.org/en/latest/) Python library to plot a histogram of which months the scientists have birthdays in! Because it would take a long time for you to input the months of various scientists, you can use [my scientist birthday JSON file]({{ site.baseurl }}/assets/scientist_birthdays.json). Just parse out the months (if you don't know how, I suggest looking at the [previous exercise]({{ site.baseurl }}{% post_url 2017-02-28-35-birthday-months %}) or [its solution]({{ site.baseurl }}{% post_url 2017-03-19-35-birthday-months-solutions %})) and draw your histogram.

If you are using a purely web-based interface for coding, this exercise won't work for you! Now might be a good time to [install Python on your own computer]().

# Discussion

Today's topic is going to be about the [bokeh](http://bokeh.pydata.org/en/latest/) Python library. Sometimes it is really nice to write code or algorithms from scratch to learn and practice. And sometimes, someone has already written the code so well that you should use theirs. Bokeh is one of these libraries - it is library specifically with functions for making plots, based on the famous [D3.js](https://d3js.org/) library originally developed at the New York Times for their visualizations.

## Plotting libraries in Python

If you are looking for a plotting library in Python, you have two main options: [matplotlib](http://matplotlib.org/) and [bokeh](http://bokeh.pydata.org/en/latest/). Today I want to discuss bokeh, because I think it will become more popular in years to come.

Many Python developers (and especially data scientists and researchers) will tell you that the most commonly used plotting library in Python is [matplotlib](http://matplotlib.org/). I myself was a matplotlib user for many years - the integrations with Python data libraries are great, and migrating from the MATLAB plotting environment to matplotlib is easy. But a friend introduced me to bokeh and I was hooked ever since. Because it is based on D3.js, the visualizations look smooth and professional.

There is no one "best" plotting library - you should use whichever one feels and looks better for you.

## When to make plots

We use plots to convey information. From this histogram:

![US Government spending histogram]({{ site.baseurl }}/assets/imgs/united-states-government-spending.png)

You can immediately see that the US government spending has been steadily increasing, reaching a peak in January 2017.

So learning how to make plots will help you become better at displaying and communicating information, both to yourself and to others.

## Installing bokeh

To use bokeh, we first have to install it. Unlike something like [`json`](https://docs.python.org/3/library/json.html) or [`Counter`](https://docs.python.org/3/library/collections.html#collections.Counter) from previous exercises, bokeh does not come installed with Python.

If you are using the [Anaconda Python](https://www.continuum.io/downloads) distribution (which you should, if you are on Windows!) then you can install bokeh by typing 

{% highlight bash %}
conda install bokeh
{% endhighlight %}

in the Windows command prompt or the bash shell.

On OSX or GNU / Linux, just type

{% highlight bash %}
pip install bokeh
{% endhighlight %}

(If you have Python 2 and Python 3 installations side by side you might have to do `pip3 install bokeh` to specifically install it for Python 3.)

## Using bokeh

The basic idea of any plotting package is simple:

1. Load the data
2. Display the data

So the first thing you have to do is prepare some data. Usually, when you are plotting data you have two axes, or groups of data, an x-axis (or horizontal axis) and a y-axis (or vertical axis). The `x` variable is your input (independent) variable and the `y` variable is your output (dependent) axis.

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

One awesome feature of Bokeh is that it gives you a toolbar you can use to play with the graph - moving it around, zooming out, saving it, etc. Plus, you can put it directly into am HTMl page!

It will look something like this:

<div class="bk-root">
<div class="bk-plotdiv" id="fa8b6ef4-9975-4340-b186-a5805260584a"></div>
</div>

<script type="text/javascript">
(function() {
var fn = function() {
Bokeh.safely(function() {
  var docs_json = {"cc36959c-d32c-4dad-9d9c-f7d4be84e19c":{"roots":{"references":[{"attributes":{"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"}},"id":"4a88da62-bf81-46c0-81bf-6b252e00cefe","type":"WheelZoomTool"},{"attributes":{"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"}},"id":"287747df-fdb1-4316-9129-65df1914062f","type":"HelpTool"},{"attributes":{},"id":"f3a3712a-e364-4f3c-b81a-8c78aea8bec5","type":"BasicTickFormatter"},{"attributes":{"callback":null},"id":"e55dbc9b-bc42-4a04-ab82-6f541572cf50","type":"DataRange1d"},{"attributes":{"callback":null,"column_names":["top","x"],"data":{"top":[4,5,6],"x":[10,20,30]}},"id":"75b1c768-37a5-47b8-baa8-4f9ba647797b","type":"ColumnDataSource"},{"attributes":{"bottom_units":"screen","fill_alpha":{"value":0.5},"fill_color":{"value":"lightgrey"},"left_units":"screen","level":"overlay","line_alpha":{"value":1.0},"line_color":{"value":"black"},"line_dash":[4,4],"line_width":{"value":2},"plot":null,"render_mode":"css","right_units":"screen","top_units":"screen"},"id":"fa6279b2-3c49-4b11-8049-4ece93c03d71","type":"BoxAnnotation"},{"attributes":{"fill_alpha":{"value":0.1},"fill_color":{"value":"#1f77b4"},"line_alpha":{"value":0.1},"line_color":{"value":"#1f77b4"},"top":{"field":"top"},"width":{"value":0.5},"x":{"field":"x"}},"id":"ed966b5c-39cd-42fe-be00-aad7a5ed73d3","type":"VBar"},{"attributes":{},"id":"7498ef8f-be9c-4f96-b6e6-573f70ba9cd2","type":"BasicTickFormatter"},{"attributes":{},"id":"2871e3ff-2dc7-4a8e-816e-af6de4adb859","type":"ToolEvents"},{"attributes":{"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"},"ticker":{"id":"915c0134-9a10-4fb7-9fae-2845e41e0daf","type":"BasicTicker"}},"id":"63511cbe-0fc9-4050-aea3-2d4ee2e699eb","type":"Grid"},{"attributes":{"dimension":1,"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"},"ticker":{"id":"c99bfc16-8bac-4fa1-a2b4-95f98476932a","type":"BasicTicker"}},"id":"3e7a9773-fdc5-4d70-a37c-45b6f907ca2d","type":"Grid"},{"attributes":{"formatter":{"id":"7498ef8f-be9c-4f96-b6e6-573f70ba9cd2","type":"BasicTickFormatter"},"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"},"ticker":{"id":"c99bfc16-8bac-4fa1-a2b4-95f98476932a","type":"BasicTicker"}},"id":"054b1213-2cac-4424-a3d1-9b70c46df995","type":"LinearAxis"},{"attributes":{},"id":"915c0134-9a10-4fb7-9fae-2845e41e0daf","type":"BasicTicker"},{"attributes":{"formatter":{"id":"f3a3712a-e364-4f3c-b81a-8c78aea8bec5","type":"BasicTickFormatter"},"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"},"ticker":{"id":"915c0134-9a10-4fb7-9fae-2845e41e0daf","type":"BasicTicker"}},"id":"19467bb8-5807-45e3-b7e6-2259354ded0f","type":"LinearAxis"},{"attributes":{},"id":"c99bfc16-8bac-4fa1-a2b4-95f98476932a","type":"BasicTicker"},{"attributes":{"active_drag":"auto","active_scroll":"auto","active_tap":"auto","tools":[{"id":"770bf549-ee40-44be-a307-f701dffe259b","type":"PanTool"},{"id":"4a88da62-bf81-46c0-81bf-6b252e00cefe","type":"WheelZoomTool"},{"id":"b39f94dd-8af5-456f-81a9-e41297a29730","type":"BoxZoomTool"},{"id":"1205914b-ffb2-4d0a-89a2-1b216ce5c3dd","type":"SaveTool"},{"id":"1b64eddb-b515-4a9b-990d-efc338803e38","type":"ResetTool"},{"id":"287747df-fdb1-4316-9129-65df1914062f","type":"HelpTool"}]},"id":"d9f4290f-5eec-4bca-a125-d312f108651b","type":"Toolbar"},{"attributes":{"data_source":{"id":"75b1c768-37a5-47b8-baa8-4f9ba647797b","type":"ColumnDataSource"},"glyph":{"id":"51cb9f5e-a787-4b98-9dec-127975ca5661","type":"VBar"},"hover_glyph":null,"nonselection_glyph":{"id":"ed966b5c-39cd-42fe-be00-aad7a5ed73d3","type":"VBar"},"selection_glyph":null},"id":"5237b1ce-ca2b-492b-92dc-a841c5cf4172","type":"GlyphRenderer"},{"attributes":{"below":[{"id":"19467bb8-5807-45e3-b7e6-2259354ded0f","type":"LinearAxis"}],"left":[{"id":"054b1213-2cac-4424-a3d1-9b70c46df995","type":"LinearAxis"}],"renderers":[{"id":"19467bb8-5807-45e3-b7e6-2259354ded0f","type":"LinearAxis"},{"id":"63511cbe-0fc9-4050-aea3-2d4ee2e699eb","type":"Grid"},{"id":"054b1213-2cac-4424-a3d1-9b70c46df995","type":"LinearAxis"},{"id":"3e7a9773-fdc5-4d70-a37c-45b6f907ca2d","type":"Grid"},{"id":"fa6279b2-3c49-4b11-8049-4ece93c03d71","type":"BoxAnnotation"},{"id":"5237b1ce-ca2b-492b-92dc-a841c5cf4172","type":"GlyphRenderer"}],"title":{"id":"def9594b-12a8-4f27-9d0f-53b6d21572aa","type":"Title"},"tool_events":{"id":"2871e3ff-2dc7-4a8e-816e-af6de4adb859","type":"ToolEvents"},"toolbar":{"id":"d9f4290f-5eec-4bca-a125-d312f108651b","type":"Toolbar"},"x_range":{"id":"ac93d5bd-93ad-4264-8b71-bf81e751b771","type":"DataRange1d"},"y_range":{"id":"e55dbc9b-bc42-4a04-ab82-6f541572cf50","type":"DataRange1d"}},"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"},{"attributes":{"plot":null,"text":""},"id":"def9594b-12a8-4f27-9d0f-53b6d21572aa","type":"Title"},{"attributes":{"fill_color":{"value":"#1f77b4"},"line_color":{"value":"#1f77b4"},"top":{"field":"top"},"width":{"value":0.5},"x":{"field":"x"}},"id":"51cb9f5e-a787-4b98-9dec-127975ca5661","type":"VBar"},{"attributes":{"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"}},"id":"1b64eddb-b515-4a9b-990d-efc338803e38","type":"ResetTool"},{"attributes":{"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"}},"id":"770bf549-ee40-44be-a307-f701dffe259b","type":"PanTool"},{"attributes":{"callback":null},"id":"ac93d5bd-93ad-4264-8b71-bf81e751b771","type":"DataRange1d"},{"attributes":{"overlay":{"id":"fa6279b2-3c49-4b11-8049-4ece93c03d71","type":"BoxAnnotation"},"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"}},"id":"b39f94dd-8af5-456f-81a9-e41297a29730","type":"BoxZoomTool"},{"attributes":{"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"}},"id":"1205914b-ffb2-4d0a-89a2-1b216ce5c3dd","type":"SaveTool"}],"root_ids":["ae08d56f-af3d-4335-a117-c4ba6a1b4225"]},"title":"Bokeh Application","version":"0.12.4"}};
  var render_items = [{"docid":"cc36959c-d32c-4dad-9d9c-f7d4be84e19c","elementid":"fa8b6ef4-9975-4340-b186-a5805260584a","modelid":"ae08d56f-af3d-4335-a117-c4ba6a1b4225"}];
  
  Bokeh.embed.embed_items(docs_json, render_items);
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

<div class="bk-root">
<div class="bk-plotdiv" id="47b88153-04c6-48ac-a1be-32237e701537"></div>
</div>

<script type="text/javascript">
(function() {
var fn = function() {
Bokeh.safely(function() {
  var docs_json = {"3e340364-756e-4163-a79c-7d94add8aa46":{"roots":{"references":[{"attributes":{"plot":{"id":"5ac61c92-da7f-443c-afe1-86ee485b22a8","subtype":"Figure","type":"Plot"}},"id":"7c532a2f-0a96-4d10-8333-1b2506fbe5ff","type":"ResetTool"},{"attributes":{"active_drag":"auto","active_scroll":"auto","active_tap":"auto","tools":[{"id":"770bf549-ee40-44be-a307-f701dffe259b","type":"PanTool"},{"id":"4a88da62-bf81-46c0-81bf-6b252e00cefe","type":"WheelZoomTool"},{"id":"b39f94dd-8af5-456f-81a9-e41297a29730","type":"BoxZoomTool"},{"id":"1205914b-ffb2-4d0a-89a2-1b216ce5c3dd","type":"SaveTool"},{"id":"1b64eddb-b515-4a9b-990d-efc338803e38","type":"ResetTool"},{"id":"287747df-fdb1-4316-9129-65df1914062f","type":"HelpTool"}]},"id":"d9f4290f-5eec-4bca-a125-d312f108651b","type":"Toolbar"},{"attributes":{"formatter":{"id":"8590bd8a-2efa-4541-9437-8d48d0db0cb1","type":"BasicTickFormatter"},"plot":{"id":"5ac61c92-da7f-443c-afe1-86ee485b22a8","subtype":"Figure","type":"Plot"},"ticker":{"id":"c590971f-3ae2-46a6-b7d8-247f7d6c0db1","type":"BasicTicker"}},"id":"7b88ac33-c909-478f-8002-b83901b9a227","type":"LinearAxis"},{"attributes":{},"id":"7efdd91e-4676-433a-b38c-b05e5cd23396","type":"ToolEvents"},{"attributes":{"bottom_units":"screen","fill_alpha":{"value":0.5},"fill_color":{"value":"lightgrey"},"left_units":"screen","level":"overlay","line_alpha":{"value":1.0},"line_color":{"value":"black"},"line_dash":[4,4],"line_width":{"value":2},"plot":null,"render_mode":"css","right_units":"screen","top_units":"screen"},"id":"fa6279b2-3c49-4b11-8049-4ece93c03d71","type":"BoxAnnotation"},{"attributes":{"fill_alpha":{"value":0.1},"fill_color":{"value":"#1f77b4"},"line_alpha":{"value":0.1},"line_color":{"value":"#1f77b4"},"top":{"field":"top"},"width":{"value":0.5},"x":{"field":"x"}},"id":"ed966b5c-39cd-42fe-be00-aad7a5ed73d3","type":"VBar"},{"attributes":{},"id":"2871e3ff-2dc7-4a8e-816e-af6de4adb859","type":"ToolEvents"},{"attributes":{"bottom_units":"screen","fill_alpha":{"value":0.5},"fill_color":{"value":"lightgrey"},"left_units":"screen","level":"overlay","line_alpha":{"value":1.0},"line_color":{"value":"black"},"line_dash":[4,4],"line_width":{"value":2},"plot":null,"render_mode":"css","right_units":"screen","top_units":"screen"},"id":"b9d02689-ebd8-4b76-a148-c890c877d318","type":"BoxAnnotation"},{"attributes":{},"id":"dd93a429-501c-4630-99ce-c4dfe789fa38","type":"CategoricalTicker"},{"attributes":{"dimension":1,"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"},"ticker":{"id":"c99bfc16-8bac-4fa1-a2b4-95f98476932a","type":"BasicTicker"}},"id":"3e7a9773-fdc5-4d70-a37c-45b6f907ca2d","type":"Grid"},{"attributes":{"plot":{"id":"5ac61c92-da7f-443c-afe1-86ee485b22a8","subtype":"Figure","type":"Plot"}},"id":"559e7cae-b2a1-463b-86ad-84ff29e9ece4","type":"HelpTool"},{"attributes":{"formatter":{"id":"f3a3712a-e364-4f3c-b81a-8c78aea8bec5","type":"BasicTickFormatter"},"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"},"ticker":{"id":"915c0134-9a10-4fb7-9fae-2845e41e0daf","type":"BasicTicker"}},"id":"19467bb8-5807-45e3-b7e6-2259354ded0f","type":"LinearAxis"},{"attributes":{},"id":"c99bfc16-8bac-4fa1-a2b4-95f98476932a","type":"BasicTicker"},{"attributes":{"fill_alpha":{"value":0.1},"fill_color":{"value":"#1f77b4"},"line_alpha":{"value":0.1},"line_color":{"value":"#1f77b4"},"top":{"field":"top"},"width":{"value":0.5},"x":{"field":"x"}},"id":"3bd5a60d-deef-4735-94ec-e9cd3433e6c3","type":"VBar"},{"attributes":{"data_source":{"id":"75b1c768-37a5-47b8-baa8-4f9ba647797b","type":"ColumnDataSource"},"glyph":{"id":"51cb9f5e-a787-4b98-9dec-127975ca5661","type":"VBar"},"hover_glyph":null,"nonselection_glyph":{"id":"ed966b5c-39cd-42fe-be00-aad7a5ed73d3","type":"VBar"},"selection_glyph":null},"id":"5237b1ce-ca2b-492b-92dc-a841c5cf4172","type":"GlyphRenderer"},{"attributes":{},"id":"8590bd8a-2efa-4541-9437-8d48d0db0cb1","type":"BasicTickFormatter"},{"attributes":{"plot":{"id":"5ac61c92-da7f-443c-afe1-86ee485b22a8","subtype":"Figure","type":"Plot"}},"id":"dfc5e6a6-5a4d-4a80-b4be-d099d5ac4d82","type":"PanTool"},{"attributes":{"callback":null},"id":"93d4e256-4c30-4b6f-b1c0-926666733975","type":"DataRange1d"},{"attributes":{"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"}},"id":"1b64eddb-b515-4a9b-990d-efc338803e38","type":"ResetTool"},{"attributes":{"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"}},"id":"770bf549-ee40-44be-a307-f701dffe259b","type":"PanTool"},{"attributes":{"dimension":1,"plot":{"id":"5ac61c92-da7f-443c-afe1-86ee485b22a8","subtype":"Figure","type":"Plot"},"ticker":{"id":"c590971f-3ae2-46a6-b7d8-247f7d6c0db1","type":"BasicTicker"}},"id":"a574df79-6eb5-44cf-a9e1-94ffb9a72fd3","type":"Grid"},{"attributes":{"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"}},"id":"1205914b-ffb2-4d0a-89a2-1b216ce5c3dd","type":"SaveTool"},{"attributes":{"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"}},"id":"4a88da62-bf81-46c0-81bf-6b252e00cefe","type":"WheelZoomTool"},{"attributes":{"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"}},"id":"287747df-fdb1-4316-9129-65df1914062f","type":"HelpTool"},{"attributes":{},"id":"f3a3712a-e364-4f3c-b81a-8c78aea8bec5","type":"BasicTickFormatter"},{"attributes":{"data_source":{"id":"f6b87d25-cea1-4073-96b2-f5755e963b01","type":"ColumnDataSource"},"glyph":{"id":"39623598-6b64-44c1-9874-a5b6226eafe1","type":"VBar"},"hover_glyph":null,"nonselection_glyph":{"id":"3bd5a60d-deef-4735-94ec-e9cd3433e6c3","type":"VBar"},"selection_glyph":null},"id":"9adf3126-40bd-4ddd-a68b-b02c9e568922","type":"GlyphRenderer"},{"attributes":{"plot":{"id":"5ac61c92-da7f-443c-afe1-86ee485b22a8","subtype":"Figure","type":"Plot"},"ticker":{"id":"dd93a429-501c-4630-99ce-c4dfe789fa38","type":"CategoricalTicker"}},"id":"d0e862ca-aa6c-482e-833a-653a564b3c42","type":"Grid"},{"attributes":{"plot":{"id":"5ac61c92-da7f-443c-afe1-86ee485b22a8","subtype":"Figure","type":"Plot"}},"id":"8258297b-6909-4722-9553-c078926793ad","type":"SaveTool"},{"attributes":{},"id":"68e488b2-5ed4-4d6f-ad7b-203ee81bec0d","type":"CategoricalTickFormatter"},{"attributes":{"callback":null},"id":"ac93d5bd-93ad-4264-8b71-bf81e751b771","type":"DataRange1d"},{"attributes":{"overlay":{"id":"b9d02689-ebd8-4b76-a148-c890c877d318","type":"BoxAnnotation"},"plot":{"id":"5ac61c92-da7f-443c-afe1-86ee485b22a8","subtype":"Figure","type":"Plot"}},"id":"ae48b828-00e2-4b64-ba92-efc97f0b7dc4","type":"BoxZoomTool"},{"attributes":{},"id":"7498ef8f-be9c-4f96-b6e6-573f70ba9cd2","type":"BasicTickFormatter"},{"attributes":{"callback":null,"column_names":["top","x"],"data":{"top":[4,5,6],"x":["a","d","e"]}},"id":"f6b87d25-cea1-4073-96b2-f5755e963b01","type":"ColumnDataSource"},{"attributes":{"active_drag":"auto","active_scroll":"auto","active_tap":"auto","tools":[{"id":"dfc5e6a6-5a4d-4a80-b4be-d099d5ac4d82","type":"PanTool"},{"id":"89a347c5-c42e-4213-a90d-9767fc144c11","type":"WheelZoomTool"},{"id":"ae48b828-00e2-4b64-ba92-efc97f0b7dc4","type":"BoxZoomTool"},{"id":"8258297b-6909-4722-9553-c078926793ad","type":"SaveTool"},{"id":"7c532a2f-0a96-4d10-8333-1b2506fbe5ff","type":"ResetTool"},{"id":"559e7cae-b2a1-463b-86ad-84ff29e9ece4","type":"HelpTool"}]},"id":"595835db-b1e5-42ed-8dce-df558d525170","type":"Toolbar"},{"attributes":{"plot":{"id":"5ac61c92-da7f-443c-afe1-86ee485b22a8","subtype":"Figure","type":"Plot"}},"id":"89a347c5-c42e-4213-a90d-9767fc144c11","type":"WheelZoomTool"},{"attributes":{"formatter":{"id":"7498ef8f-be9c-4f96-b6e6-573f70ba9cd2","type":"BasicTickFormatter"},"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"},"ticker":{"id":"c99bfc16-8bac-4fa1-a2b4-95f98476932a","type":"BasicTicker"}},"id":"054b1213-2cac-4424-a3d1-9b70c46df995","type":"LinearAxis"},{"attributes":{},"id":"c590971f-3ae2-46a6-b7d8-247f7d6c0db1","type":"BasicTicker"},{"attributes":{"callback":null,"factors":["a","b","c","d","e"]},"id":"66aa90e0-099b-478b-a34e-458a60fb2c87","type":"FactorRange"},{"attributes":{},"id":"915c0134-9a10-4fb7-9fae-2845e41e0daf","type":"BasicTicker"},{"attributes":{"fill_color":{"value":"#1f77b4"},"line_color":{"value":"#1f77b4"},"top":{"field":"top"},"width":{"value":0.5},"x":{"field":"x"}},"id":"39623598-6b64-44c1-9874-a5b6226eafe1","type":"VBar"},{"attributes":{"callback":null},"id":"e55dbc9b-bc42-4a04-ab82-6f541572cf50","type":"DataRange1d"},{"attributes":{"plot":null,"text":""},"id":"c8955b21-19f2-4d17-a134-9021d7fae70c","type":"Title"},{"attributes":{"below":[{"id":"ebcfb431-5268-4857-b085-f0a73bf109a2","type":"CategoricalAxis"}],"left":[{"id":"7b88ac33-c909-478f-8002-b83901b9a227","type":"LinearAxis"}],"renderers":[{"id":"ebcfb431-5268-4857-b085-f0a73bf109a2","type":"CategoricalAxis"},{"id":"d0e862ca-aa6c-482e-833a-653a564b3c42","type":"Grid"},{"id":"7b88ac33-c909-478f-8002-b83901b9a227","type":"LinearAxis"},{"id":"a574df79-6eb5-44cf-a9e1-94ffb9a72fd3","type":"Grid"},{"id":"b9d02689-ebd8-4b76-a148-c890c877d318","type":"BoxAnnotation"},{"id":"9adf3126-40bd-4ddd-a68b-b02c9e568922","type":"GlyphRenderer"}],"title":{"id":"c8955b21-19f2-4d17-a134-9021d7fae70c","type":"Title"},"tool_events":{"id":"7efdd91e-4676-433a-b38c-b05e5cd23396","type":"ToolEvents"},"toolbar":{"id":"595835db-b1e5-42ed-8dce-df558d525170","type":"Toolbar"},"x_range":{"id":"66aa90e0-099b-478b-a34e-458a60fb2c87","type":"FactorRange"},"y_range":{"id":"93d4e256-4c30-4b6f-b1c0-926666733975","type":"DataRange1d"}},"id":"5ac61c92-da7f-443c-afe1-86ee485b22a8","subtype":"Figure","type":"Plot"},{"attributes":{"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"},"ticker":{"id":"915c0134-9a10-4fb7-9fae-2845e41e0daf","type":"BasicTicker"}},"id":"63511cbe-0fc9-4050-aea3-2d4ee2e699eb","type":"Grid"},{"attributes":{"below":[{"id":"19467bb8-5807-45e3-b7e6-2259354ded0f","type":"LinearAxis"}],"left":[{"id":"054b1213-2cac-4424-a3d1-9b70c46df995","type":"LinearAxis"}],"renderers":[{"id":"19467bb8-5807-45e3-b7e6-2259354ded0f","type":"LinearAxis"},{"id":"63511cbe-0fc9-4050-aea3-2d4ee2e699eb","type":"Grid"},{"id":"054b1213-2cac-4424-a3d1-9b70c46df995","type":"LinearAxis"},{"id":"3e7a9773-fdc5-4d70-a37c-45b6f907ca2d","type":"Grid"},{"id":"fa6279b2-3c49-4b11-8049-4ece93c03d71","type":"BoxAnnotation"},{"id":"5237b1ce-ca2b-492b-92dc-a841c5cf4172","type":"GlyphRenderer"}],"title":{"id":"def9594b-12a8-4f27-9d0f-53b6d21572aa","type":"Title"},"tool_events":{"id":"2871e3ff-2dc7-4a8e-816e-af6de4adb859","type":"ToolEvents"},"toolbar":{"id":"d9f4290f-5eec-4bca-a125-d312f108651b","type":"Toolbar"},"x_range":{"id":"ac93d5bd-93ad-4264-8b71-bf81e751b771","type":"DataRange1d"},"y_range":{"id":"e55dbc9b-bc42-4a04-ab82-6f541572cf50","type":"DataRange1d"}},"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"},{"attributes":{"plot":null,"text":""},"id":"def9594b-12a8-4f27-9d0f-53b6d21572aa","type":"Title"},{"attributes":{"fill_color":{"value":"#1f77b4"},"line_color":{"value":"#1f77b4"},"top":{"field":"top"},"width":{"value":0.5},"x":{"field":"x"}},"id":"51cb9f5e-a787-4b98-9dec-127975ca5661","type":"VBar"},{"attributes":{"callback":null,"column_names":["top","x"],"data":{"top":[4,5,6],"x":[10,20,30]}},"id":"75b1c768-37a5-47b8-baa8-4f9ba647797b","type":"ColumnDataSource"},{"attributes":{"formatter":{"id":"68e488b2-5ed4-4d6f-ad7b-203ee81bec0d","type":"CategoricalTickFormatter"},"plot":{"id":"5ac61c92-da7f-443c-afe1-86ee485b22a8","subtype":"Figure","type":"Plot"},"ticker":{"id":"dd93a429-501c-4630-99ce-c4dfe789fa38","type":"CategoricalTicker"}},"id":"ebcfb431-5268-4857-b085-f0a73bf109a2","type":"CategoricalAxis"},{"attributes":{"overlay":{"id":"fa6279b2-3c49-4b11-8049-4ece93c03d71","type":"BoxAnnotation"},"plot":{"id":"ae08d56f-af3d-4335-a117-c4ba6a1b4225","subtype":"Figure","type":"Plot"}},"id":"b39f94dd-8af5-456f-81a9-e41297a29730","type":"BoxZoomTool"}],"root_ids":["ae08d56f-af3d-4335-a117-c4ba6a1b4225","5ac61c92-da7f-443c-afe1-86ee485b22a8"]},"title":"Bokeh Application","version":"0.12.4"}};
  var render_items = [{"docid":"3e340364-756e-4163-a79c-7d94add8aa46","elementid":"47b88153-04c6-48ac-a1be-32237e701537","modelid":"5ac61c92-da7f-443c-afe1-86ee485b22a8"}];
  
  Bokeh.embed.embed_items(docs_json, render_items);
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
