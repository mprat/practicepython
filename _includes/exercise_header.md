{% assign solution = site.categories.solution | where: "number", include.number | last %}
{% if solution == blank %}
	{% assign solution_url = "/solution/comingsoon" %}
{% else %}
	{% assign solution_url = solution.url %}
{% endif %}

## Exercise {{ include.number }} (and [Solution]({{ site.baseurl }}{{ solution_url }}))