---
layout: post
number: 36
chili: 3
part: 4
of: 4
part_text: birthday data
categories: [solution]
bokeh: true
---

In the [previous exercise]({{ site.baseurl }}{% post_url 2017-02-28-35-birthday-months %}) we counted how many birthdays there are in each month in our dictionary of birthdays. In this exercise, use the [bokeh](http://bokeh.pydata.org/en/latest/) Python library to plot a histogram of which months the scientists have birthdays in using [my scientist birthday JSON file]({{ site.baseurl }}/assets/scientist_birthdays.json).

## Solution

In our solution we need to:

1. Load the JSON data
2. Count the number of months
3. Plot with Bokeh

There are a few ways to do this, but here is mine:

{% highlight python %}
from collections import Counter
import json
import math

from bokeh.plotting import figure, show, output_file


DATA_FILE = "scientist_birthdays.json"
output_file("plot.html")

with open(DATA_FILE, "r") as f:
    DATA = json.load(f)

num_to_string = {
    1: "January",
    2: "February",
    3: "March",
    4: "April",
    5: "May",
    6: "June",
    7: "July",
    8: "August",
    9: "September",
    10: "October",
    11: "November",
    12: "December"
}

months = []
for name, birthday_string in DATA.items():
    month = int(birthday_string.split("/")[0])
    months.append(num_to_string[month])
months = Counter(months)

months, counts = list(zip(*months.items()))

categories = list(num_to_string.values())
p = figure(x_range=categories, title="Scientists' Birthday Months")
p.xaxis.major_label_orientation = math.pi/4
p.vbar(x=months, top=counts)

show(p)
{% endhighlight %}

And my output plot looks like this (you must have Javascript enabled to see it):

<div class="bk-root" id="24430e12-d573-4c12-b211-59666af0983f" data-root-id="1331"></div>
            
<script type="application/json" id="1499">
  {"7c2f2841-1062-4546-b0b9-1f0313d05413":{"defs":[],"roots":{"references":[{"attributes":{},"id":"1374","type":"CategoricalTickFormatter"},{"attributes":{"fill_alpha":{"value":0.1},"fill_color":{"value":"#1f77b4"},"hatch_alpha":{"value":0.1},"line_alpha":{"value":0.1},"line_color":{"value":"#1f77b4"},"top":{"field":"top"},"x":{"field":"x"}},"id":"1365","type":"VBar"},{"attributes":{},"id":"1376","type":"UnionRenderers"},{"attributes":{"source":{"id":"1363"}},"id":"1368","type":"CDSView"},{"attributes":{},"id":"1372","type":"AllLabels"},{"attributes":{"fill_alpha":{"value":0.2},"fill_color":{"value":"#1f77b4"},"hatch_alpha":{"value":0.2},"line_alpha":{"value":0.2},"line_color":{"value":"#1f77b4"},"top":{"field":"top"},"x":{"field":"x"}},"id":"1366","type":"VBar"},{"attributes":{"tools":[{"id":"1349"},{"id":"1350"},{"id":"1351"},{"id":"1352"},{"id":"1353"},{"id":"1354"}]},"id":"1356","type":"Toolbar"},{"attributes":{"fill_color":{"value":"#1f77b4"},"line_color":{"value":"#1f77b4"},"top":{"field":"top"},"x":{"field":"x"}},"id":"1364","type":"VBar"},{"attributes":{},"id":"1377","type":"Selection"},{"attributes":{"bottom_units":"screen","coordinates":null,"fill_alpha":0.5,"fill_color":"lightgrey","group":null,"left_units":"screen","level":"overlay","line_alpha":1.0,"line_color":"black","line_dash":[4,4],"line_width":2,"right_units":"screen","syncable":false,"top_units":"screen"},"id":"1355","type":"BoxAnnotation"},{"attributes":{"factors":["January","February","March","April","May","June","July","August","September","October","November","December"]},"id":"1334","type":"FactorRange"},{"attributes":{},"id":"1338","type":"CategoricalScale"},{"attributes":{},"id":"1343","type":"CategoricalTicker"},{"attributes":{},"id":"1371","type":"BasicTickFormatter"},{"attributes":{},"id":"1336","type":"DataRange1d"},{"attributes":{"coordinates":null,"group":null,"text":"Scientists' Birthday Months"},"id":"1332","type":"Title"},{"attributes":{"coordinates":null,"data_source":{"id":"1363"},"glyph":{"id":"1364"},"group":null,"hover_glyph":null,"muted_glyph":{"id":"1366"},"nonselection_glyph":{"id":"1365"},"view":{"id":"1368"}},"id":"1367","type":"GlyphRenderer"},{"attributes":{"coordinates":null,"formatter":{"id":"1371"},"group":null,"major_label_policy":{"id":"1372"},"ticker":{"id":"1346"}},"id":"1345","type":"LinearAxis"},{"attributes":{},"id":"1375","type":"AllLabels"},{"attributes":{},"id":"1340","type":"LinearScale"},{"attributes":{},"id":"1353","type":"ResetTool"},{"attributes":{"axis":{"id":"1342"},"coordinates":null,"group":null,"ticker":null},"id":"1344","type":"Grid"},{"attributes":{"below":[{"id":"1342"}],"center":[{"id":"1344"},{"id":"1348"}],"left":[{"id":"1345"}],"renderers":[{"id":"1367"}],"title":{"id":"1332"},"toolbar":{"id":"1356"},"x_range":{"id":"1334"},"x_scale":{"id":"1338"},"y_range":{"id":"1336"},"y_scale":{"id":"1340"}},"id":"1331","subtype":"Figure","type":"Plot"},{"attributes":{},"id":"1352","type":"SaveTool"},{"attributes":{},"id":"1354","type":"HelpTool"},{"attributes":{"overlay":{"id":"1355"}},"id":"1351","type":"BoxZoomTool"},{"attributes":{"coordinates":null,"formatter":{"id":"1374"},"group":null,"major_label_orientation":0.7853981633974483,"major_label_policy":{"id":"1375"},"ticker":{"id":"1343"}},"id":"1342","type":"CategoricalAxis"},{"attributes":{},"id":"1349","type":"PanTool"},{"attributes":{},"id":"1350","type":"WheelZoomTool"},{"attributes":{"data":{"top":[1,1,1],"x":["March","December","January"]},"selected":{"id":"1377"},"selection_policy":{"id":"1376"}},"id":"1363","type":"ColumnDataSource"},{"attributes":{},"id":"1346","type":"BasicTicker"},{"attributes":{"axis":{"id":"1345"},"coordinates":null,"dimension":1,"group":null,"ticker":null},"id":"1348","type":"Grid"}],"root_ids":["1331"]},"title":"Bokeh Application","version":"2.4.2"}}
</script>
<script type="text/javascript">
  (function() {
    const fn = function() {
      Bokeh.safely(function() {
        (function(root) {
          function embed_document(root) {
            
          const docs_json = document.getElementById('1499').textContent;
          const render_items = [{"docid":"7c2f2841-1062-4546-b0b9-1f0313d05413","root_ids":["1331"],"roots":{"1331":"24430e12-d573-4c12-b211-59666af0983f"}}];
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

One interesting syntax is the line `months, counts = list(zip(*months.items()))`. What this does is takes the `months` dictionary, returns it as tuples, then unzips them into two lists. We can see this output by looking at the individual outputs one at a time in the shell:

```
In [1]: months
Out[1]: Counter({'March': 1, 'December': 1, 'January': 1})

In [2]: months.items()
Out[2]: dict_items([('March', 1), ('December', 1), ('January', 1)])

In [3]: zip(*months.items())
Out[3]: <zip at 0x7fed18fd8040>

In [4]: list(zip(*months.items()))
Out[4]: [('March', 'December', 'January'), (1, 1, 1)]
```

The end result is two lists, one for the months and one for the counts, that are in the correct order.

Happy coding!
