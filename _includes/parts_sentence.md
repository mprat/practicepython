{% assign posts = site.categories.exercise | where_exp:"p", "p.part_text == include.part_text" | sort 'part' %}
{% assign second_to_last = include.part_of | minus: 1 %}

<p>
<i>This exercise is Part {{ include.part }} of {{ include.part_of }} of the {{ include.part_text }} exercise series. The other exercises are: {% for part_num in (1..include.part_of) %}{% assign post = posts | where:"part", part_num | last %}{% if post %}{% assign link = post.url %}{% else %}{% assign link = "/exercise/comingsoon" %}{% endif %}{% if part_num != include.part %}{% if part_num == include.part_of %}and <a href="{{ site.baseurl}}{{ link }}">Part {{ part_num }}</a>.</i>{% elsif include.part == include.part_of and part_num == second_to_last %}and <a href="{{ site.baseurl}}{{ link }}">Part {{ part_num }}</a>.</i>{% else %}<a href="{{ site.baseurl}}{{ link }}">Part {{ part_num }}</a>{% if second_to_last != 2 %},{% endif %} {% endif %}{% endif %}{% endfor %}
</p>