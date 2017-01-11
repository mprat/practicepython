<div class="left">
<h2 class="midheader"> All Exercises</h2>
<ul>
  {% for post in site.categories.exercise %}
    <li>
      {{ post.number }}: <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title | replace: '1', '' | replace: '2', '' | replace: '3', '' | replace: '4', '' | replace: '5', ''  | replace: '6', '' | replace: '7', '' | replace: '8', ''  | replace: '9', ''  | replace: '0', '' }}</a>
      {% if post.chili %}
        {% include chili.md chilis=post.chili %}
      {% endif %}
    </li>
  {% endfor %}
</ul>
</div>

<div class="right">
<h2 class="midheader"> All Solutions</h2>
<ul>
  {% assign count = site.categories.exercise.size %}
  {% assign solist = (site.categories.solution | sort: 'title') %}
  {% for post in solist reversed %}
    {% if post.number != count %}
        {% assign diff = count | minus: post.number %}
        {% for num in (1..diff) %}
          <li>{{ count }}: Coming soon!</li>
          {% capture count %}{{ count | minus: 1}}{% endcapture %}
        {% endfor %}
    {% endif %}
    <li>{{ post.number }}: <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title | replace: '1', '' | replace: '2', '' | replace: '3', '' | replace: '4', '' | replace: '5', ''  | replace: '6', '' | replace: '7', '' | replace: '8', ''  | replace: '9', ''  | replace: '0', '' }}</a></li>
    {% capture count %}{{ count | minus: 1}}{% endcapture %}
  {% endfor %}
</ul>
</div>