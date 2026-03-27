# Testival

Software testing community meetups and conferences.

Links: [Meetup](https://www.meetup.com/testival/) [GitHub](https://github.com/zeljkofilipin/testival)

Pages: [Home](/) [Tags](/tags/) [Authors](/authors/)

{% assign tag_names = "" | split: "" -%}
{%- for tag in site.tags -%}
{%- assign tag_name_str = tag[0] | append: "" -%}
{%- assign tag_names = tag_names | push: tag_name_str -%}
{%- endfor -%}
{%- assign tag_names = tag_names | sort -%}
Tags:
{%- for name in tag_names %} [{{ name }}](/tags/#{{ name }})
{%- endfor %}

{% assign authors = "" | split: "" -%}
{%- for post in site.posts -%}
{%- unless authors contains post.author -%}
{%- assign authors = authors | push: post.author -%}
{%- endunless -%}
{%- endfor -%}
{%- assign authors = authors | sort -%}
Authors:
{%- for author in authors %} [{{ author }}](/authors/#{{ author | slugify }})
{%- endfor %}
