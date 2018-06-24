---
layout: default
title: 我的博客列表
---

## 你好，欢迎访问我的主页 6

<ul>

　　　　{% for post in site.posts %}

　　　　　　<li>{{ post.date | date_to_string }} <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>

　　　　{% endfor %}

</ul>
