---
layout: default
title: "归档：Archives"
---
<ul class="list-unstyled">
     {% for post in site.posts limit:100 %} 
	 {% unless post.next %} 
    <h2>{{ post.date | date: '%Y' }}</h2> 
	{% else %} {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %} {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %} 
	{% if year != nyear %} 
    <h2>{{ post.date | date: '%Y' }}</h2> {% endif %} 
	{% endunless %} 
    <li><h4><span class="btn-group" style="min-width: 108px;">{{ post.date | date_to_string }}</span> &raquo;&nbsp;&nbsp;<a href="{{ post.url }}">{{ post.title }}</a></h4></li> 
	{% endfor %} 
</ul> 
