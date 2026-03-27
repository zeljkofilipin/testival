# Testival

Software testing community meetups and conferences.

Links: [Meetup](https://www.meetup.com/testival/) [GitHub](https://github.com/zeljkofilipin/testival)

Pages: [Home](/) [Tags](/tags/)

{% assign tag_names = "" | split: "" -%}
{%- for tag in site.tags -%}
{%- assign tag_names = tag_names | push: tag[0] -%}
{%- endfor -%}
{%- assign tag_names = tag_names | sort | reverse -%}
Tags:
{%- for name in tag_names %} [{{ name }}](/tags/#{{ name }})
{%- endfor %}
