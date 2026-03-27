---
layout: default
permalink: /authors/
---

{% include header.md %}

{% assign authors = "" | split: "" %}
{% for post in site.posts %}
{% unless authors contains post.author %}
{% assign authors = authors | push: post.author %}
{% endunless %}
{% endfor %}
{% assign authors = authors | sort %}
{% for author in authors %}
## {{ author }}

{% for post in site.posts %}
{% if post.author == author %}
- **{{ post.date | date: "%Y-%m-%d" }}** [{{ post.title }}]({{ post.url }})
{% endif %}
{% endfor %}

{% endfor %}
