---
layout: default
permalink: /tags/
---

{% include header.md %}

{% assign tag_names = "" | split: "" %}
{% for tag in site.tags %}
{% assign tag_names = tag_names | push: tag[0] %}
{% endfor %}
{% assign tag_names = tag_names | sort | reverse %}
{% for name in tag_names %}
## {{ name }}

{% for post in site.tags[name] %}
- **{{ post.date | date: "%Y-%m-%d" }}** [{{ post.title }}]({{ post.url }})
{% endfor %}

{% endfor %}
