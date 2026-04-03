---
layout: default
---

{% include header.md %}

## Posts

{% for post in site.posts %}
- **{{ post.date | date: "%Y-%m-%d" }}** [{{ post.title }}]({{ post.url }}) *\|{% for tag in post.tags %}{% assign tag_str = tag | append: "" %} [{{ tag }}](/tags/#{{ tag_str | slugify }}){% endfor %}*
{% endfor %}
