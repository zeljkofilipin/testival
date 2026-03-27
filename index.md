---
layout: default
---

# Testival

Software testing community meetups and conferences.

Links: [Meetup](https://www.meetup.com/testival/) [GitHub](https://github.com/zeljkofilipin/testival)

Pages: [Home](/) [Tags](/tags/)

## Posts

{% for post in site.posts %}
- **{{ post.date | date: "%Y-%m-%d" }}** [{{ post.title }}]({{ post.url }})
{% endfor %}
