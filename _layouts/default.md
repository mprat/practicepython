<!DOCTYPE html>
<html>
<head>
	<title>{{ page.title }}</title>
	<meta name="viewport" content="width=device-width, height=device-height, initial-scale=1.0, minimum-scale=0.8">
	<meta name="author" content="Michele Pratusevich, michele.pratusevich@gmail.com">
	<meta charset="UTF-8">
	<link rel="stylesheet" type="text/css" href="{{ site.baseurl }}/css/main.css">
	<link rel="shortcut icon" type="image/png" href="{{ site.baseurl }}/favicon.png">

	{% if page.bokeh %}
        
		<script type="text/javascript" src="https://cdn.bokeh.org/bokeh/release/bokeh-2.4.2.min.js"></script>
	{% endif %}
</head>
<body>
<noscript id="deferred-styles">
	<link rel="stylesheet" type="text/css" href="{{ site.baseurl }}/css/syntax.css">
</noscript>

{% include header.html %}

<script>
  var loadDeferredStyles = function() {
    var addStylesNode = document.getElementById("deferred-styles");
    var replacement = document.createElement("div");
    replacement.innerHTML = addStylesNode.textContent;
    document.body.appendChild(replacement)
    addStylesNode.parentElement.removeChild(addStylesNode);
  };
  var raf = requestAnimationFrame || mozRequestAnimationFrame ||
      webkitRequestAnimationFrame || msRequestAnimationFrame;
  if (raf) raf(function() { window.setTimeout(loadDeferredStyles, 0); });
  else window.addEventListener('load', loadDeferredStyles);
</script>

<div class="boxframe center">	
	{% if page.date %}
		<h4 class="textright">{{ page.date | date_to_long_string}}</h4>
	{% endif %}

	{{ content }}
</div>

{% include footer.html %}

</body>
</html>