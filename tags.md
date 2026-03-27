---
layout: default
permalink: /tags/
---

{% include header.md %}

{% assign tag_names = "" | split: "" %}
{% for tag in site.tags %}
{% assign tag_name_str = tag[0] | append: "" %}
{% assign tag_names = tag_names | push: tag_name_str %}
{% endfor %}
{% assign tag_names = tag_names | sort %}
{% for name in tag_names %}
## {{ name }}

{% for tag in site.tags %}{% assign tag_str = tag[0] | append: "" %}{% if tag_str == name %}{% for post in tag[1] %}
- **{{ post.date | date: "%Y-%m-%d" }}** [{{ post.title }}]({{ post.url }})
{% endfor %}{% endif %}{% endfor %}

{% endfor %}
