---
layout: page
title: Blog
tagline: v1
---
{% include JB/setup %}

<ul class="posts">
  {% for post in site.posts %}
    <h3><li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li></h3>
  {% endfor %}
</ul>


