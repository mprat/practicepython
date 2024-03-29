---
layout: default
bokeh: false
---

{% if page.title and page.number %}
	<span><h1 class="pagetitle">{{ page.title | replace: '1', '' | replace: '2', '' | replace: '3', '' | replace: '4', '' | replace: '5', ''  | replace: '6', '' | replace: '7', '' | replace: '8', ''  | replace: '9', ''  | replace: '0', '' }} {% include chili.md chilis=page.chili %} </h1>
{% else %}
	<span><h1 class="pagetitle">{{ page.title }} </h1>

<!-- 	</span> <span class="flattr"><a href="https://flattr.com/submit/auto?user_id=mpratland&url={{ site.production_url }}{{ page.url }}" target="_blank"><img src="//api.flattr.com/button/flattr-badge-large.png" alt="Flattr this" title="Flattr this" border="0" width="93" height="20"></a></span> -->
{% endif %}

{% if page.tags %}
	<div>
	<i>
	{% for tag in page.tags %}
		{{ tag }}
	{% endfor %}
	</i>
	</div>
{% endif %}

{% if page.categories contains 'exercise' %}
	{% include exercise_header.md number=page.number %}
{% elsif page.categories contains 'solution' %}
	{% include solution_header.md number=page.number %}
{% endif %}

{% if page.part and page.part_text and page.of %}
	{% include parts_sentence.md part=page.part part_text=page.part_text part_of=page.of %} 
{% endif %}

{{ content }}

{% if page.categories contains 'exercise' %}
	{% include submit.md %}
{% endif %}

{% include share_icons.html %}

{% if page.title and page.number %}
	{% include previous_and_next_exercises.html current=page.number %}
{% endif %}

<br>
{% include yubico.html %}

{% if jekyll.environment == 'production' %}
	{% include comments.html %}
{% endif %}