---
layout: default
title: 我的Blog
---

# {{ page.title }}

## 最新文章2

<ul>

  {% for post in site.posts %}

    <li>{{ post.date | date_to_string }} <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>

  {% endfor %}

</ul>
