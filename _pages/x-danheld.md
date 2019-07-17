---
title: Dan Held
layout: archive
permalink: /danheld/
---


{% for author in site.data.author %}
	{% for post in site.posts | where:"author", "danheld" %}
  		<section id="{{ author.name }}" class="taxonomy__section">
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