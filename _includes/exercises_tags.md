<ul>
{% assign exercises = site.categories.exercise | sort: 'number' %}
{% for post in exercises %}
	{% if post.tags contains include.tag %}
		{% if include.use_light_text %}
			{% assign text = ' about ' | append: post.light_text %}
		{% endif %}

		{% if text == blank %}
			{% assign text = ':' | append: post.title | replace: '1', '' | replace: '2', '' | replace: '3', '' | replace: '4', '' | replace: '5', ''  | replace: '6', '' | replace: '7', '' | replace: '8', ''  | replace: '9', ''  | replace: '0', '' %}
		{% endif %}

		<li>
			<a href="({{ site.baseurl }}{{ post.url }})">Exercise {{ post.number }}{{ text }}</a> {% include chili.md chilis=post.chili %}
		</li>
	{% endif %}
{% endfor %}
</ul>