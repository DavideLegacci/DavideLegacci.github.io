

## 🏠 [To main site](https://davidelegacci.it/)

{% for tag in site.tags %}
<h3>{{ tag[0] }}</h3>
<ul>
{% for post in tag[1] %}
<li><a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>
{% endfor %}

{% for post in site.posts %}
<h2>{{ post.title }}</h2>
{{ post.excerpt }}
<a href=".{{ post.url }}">➡️ {{post.title }}</a>
{% endfor %}

