# Learning in games
<ul>
  {% for post in site.posts %}
    {% if post.tags contains "learning-in-games" %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        <small>{{ post.date | date: "%B %d, %Y" }}</small>
      </li>
    {% endif %}
  {% endfor %}
</ul>
