{% assign exercise = site.categories.exercise | where: "number", include.number | last %}

<h2><a href="{{ site.baseurl }}{{ exercise.url }}">Exercise {{ include.number }}</a></h2>