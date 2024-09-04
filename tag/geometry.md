# Geometry
<ul>
  {% for post in site.posts %}
    {% if post.tags contains "geometry" %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        <small>{{ post.date | date: "%B %d, %Y" }}</small>
      </li>
    {% endif %}
  {% endfor %}
</ul>
