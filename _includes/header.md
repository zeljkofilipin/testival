# Testival

Software testing community meetups and conferences.

Links: [Meetup](https://www.meetup.com/testival/) [GitHub](https://github.com/zeljkofilipin/testival)

{% include nav.md %}

{% assign tag_names = "" | split: "" -%}
{%- for tag in site.tags -%}
{%- assign tag_name_str = tag[0] | append: "" -%}
{%- assign tag_names = tag_names | push: tag_name_str -%}
{%- endfor -%}
{%- assign tag_names = tag_names | sort -%}
Tags:
{%- for name in tag_names -%}
{%- for tag in site.tags -%}
{%- assign tag_str = tag[0] | append: "" -%}
{%- if tag_str == name %}{% unless forloop.parentloop.first %} \|{% endunless %} [{{ name }}](/tags/#{{ name }}) *({{ tag[1].size }})*
{%- endif -%}
{%- endfor -%}
{%- endfor %}

{% assign authors = "" | split: "" -%}
{%- for post in site.posts -%}
{%- unless authors contains post.author -%}
{%- assign authors = authors | push: post.author -%}
{%- endunless -%}
{%- endfor -%}
{%- assign authors = authors | sort -%}
Authors:
{%- for author in authors -%}
{%- assign count = 0 -%}
{%- for post in site.posts -%}
{%- if post.author == author -%}
{%- assign count = count | plus: 1 -%}
{%- endif -%}
{%- endfor %}{% unless forloop.first %} \|{% endunless %} [{{ author }}](/authors/#{{ author | slugify }}) *({{ count }})*
{%- endfor %}
