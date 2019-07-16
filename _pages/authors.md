---
title: Authors
layout: category
permalink: /authors/
taxonomy: posts

---

# Posts are listed in chronological order.

# [Browse by Author or Quarter Published](https://cryptowords.github.io/tags/)
<br>

***


{% for author in site.data.authors %}
  {% for post in site.posts | where:"author",{{author.name}} %}
      <a href="{{post.url}}">{{post.title}}</a>
  {% endfor %}
{% endfor %}