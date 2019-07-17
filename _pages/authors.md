---
title: Authors
layout: default
permalink: /authors/
---

{% for author in site.data.authors %}
  {% for post in site.posts | where:"author",{{author.name}} %}
      <a href="{{post.url}}">{{post.title}}</a>
  {% endfor %}
{% endfor %}