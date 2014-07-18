<div class="left">
<h2 class="midheader"> All Exercises</h2>
<ul>
  {% for post in site.categories.exercise %}
    <li>
      <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
</div>

<div class="right">
<h2 class="midheader"> All Solutions: </h2>
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
    <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
    {% capture count %}{{ count | minus: 1}}{% endcapture %}
  {% endfor %}
</ul>
</div>