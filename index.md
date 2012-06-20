---
layout: page
title: 
tagline: Supporting tagline
---
{% include JB/setup %}

<ul class="posts" style="font-size:18px;">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>



