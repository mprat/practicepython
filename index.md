---
layout: default
title: Practice Python
---

Welcome to Practice Python! There are over {{ site.categories.exercise.size | divided_by: 10 | floor | times: 10 }} beginner Python exercises just waiting to be solved. Each exercise comes with a small discussion of a topic and a link to a solution. New exercise are posted monthly, so check back often, or follow on [Feedly](http://cloud.feedly.com/#subscription%2Ffeed%2Fhttp%3A%2F%2Fpracticepython.org%2Fatom.xml){:target="_blank"}, [Twitter](https://twitter.com/intent/follow/?screen_name={{ site.twitter.username }}){:target="_blank"}, or [your favorite RSS reader]({{ site.production_url }}/atom.xml){:target="_blank"}. To get started right away, read [more about Practice Python](/about/) or go straight to [Exercise 1]({{ site.baseurl }}{% post_url 2014-01-29-01-character-input %})!

<div class="latest">
{% for post in site.categories.exercise limit:1 %}
	<p><a href="{{ site.baseurl }}{{ post.url }}">Latest exercise</a>: Exercise {{ post.number }} on {{ post.date | date_to_long_string }}</p>

{% endfor %}


{% for post in site.categories.solution limit:1 %}
	<p><a href="{{ site.baseurl }}{{ post.url }}">Latest solution</a>: Solution {{ post.number }} on {{ post.date | date_to_long_string }}</p>

{% endfor %}

{% for post in site.categories.blog limit:1 %}
	<p><a href="{{ site.baseurl }}{{ post.url }}">Latest blog post</a>: <i>{{ post.title }}</i> on {{ post.date | date_to_long_string }}</p>

{% endfor %}

</div>

{% include amazon.html %}

{% include exercises.md %}