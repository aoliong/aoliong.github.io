## 你好，欢迎访问我的主页

{% assign image_files = site.sttic_files | where: "image", true %}
{% for myimage in image_files %}
  {{ myimage.path}}
{% endfor %}
