---
title: Dan Held
layout: single
permalink: /danheld/
---

{% for author in site.data.authors %}
  {% for post in site.posts | where:"author",{{author.danheld}} %}
      <a href="{{post.url}}">{{post.title}}</a>
  {% endfor %}
{% endfor %}