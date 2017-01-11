{% assign exercise = site.categories.exercise | where: "number", include.number | last %}

## [Exercise {{ include.number }}]({{ site.baseurl }}{{ exercise.url }})