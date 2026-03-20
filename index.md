---
layout: default
---

# Testival

Software testing community meetups and conferences.
[Meetup](https://www.meetup.com/testival/) ·
[GitHub](https://github.com/zeljkofilipin/testival)

{% for post in site.posts %}
- **{{ post.date | date: "%Y-%m-%d" }}** [{{ post.title }}]({{ post.url }})
{% endfor %}
