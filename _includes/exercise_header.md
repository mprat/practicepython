{% assign solution = site.categories.solution | where: "number", include.number | last %}
{% if solution == blank %}
	{% assign solution_url = "/solution/comingsoon" %}
{% else %}
	{% assign solution_url = solution.url %}
{% endif %}

<h2>Exercise {{ include.number }} (and <a href="{{ site.baseurl }}{{ solution_url }}">Solution</a>)</h2>