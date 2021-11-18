<div class="left">
<h2 class="midheader"> All Exercises</h2>
<ul>
  {% for post in site.categories.exercise reversed %}
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
  {% assign count = site.categories.exercise.size | minus: 1 %}
  {% assign solist = (site.categories.solution | sort: 'title') %}
  {% for index in (0..count) %}
    {% assign post = solist[index] %}
    {% if post %}
      <li>{{ index | plus: 1 }}: <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title | replace: '1', '' | replace: '2', '' | replace: '3', '' | replace: '4', '' | replace: '5', ''  | replace: '6', '' | replace: '7', '' | replace: '8', ''  | replace: '9', ''  | replace: '0', '' }}</a></li>
    {% else %}
        <li>{{ index | plus: 1 }}: Coming soon!</li>
    {% endif %}
  {% endfor %}
</ul>
</div>