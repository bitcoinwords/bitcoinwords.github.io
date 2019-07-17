---
title: Authors
layout: archive
permalink: /authors/
---

Authors listed below.


{% for author in site.data.authors %}
  {% for post in site.posts | where:"author",{{author.name}} %}
    <a href="{{post.url}}">{{post.title}}</a>
    <section id="{{ year.name }}" class="taxonomy__section">
    	<h2 class="archive__subtitle">{{ author.name }}</h2>
    	<div class="entries-{{ page.entries_layout | default: 'list' }}">
      		{% for post in year.items %}
        		{% include archive-single.html type=page.entries_layout %}
      		{% endfor %}
    	</div>
    <a href="#page-title" class="back-to-top">{{ site.data.ui-text[site.locale].back_to_top | default: 'Back to Top' }} &uarr;</a>
  </section>
  {% endfor %}
{% endfor %}