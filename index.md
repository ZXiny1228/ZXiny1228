---
layout: default
title: 首页
---

{% for post in site.posts limit:3 %}
- [{{ post.title }}]({{ post.url }})
  ({{ post.date | date: "%Y-%m-%d" }})
{% endfor %}
