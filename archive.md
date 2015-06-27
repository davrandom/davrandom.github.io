---
layout: page
title: "Archive"
comments: true
sharing: true
footer: true
---


<ul class="posts">
{% assign year = "" %}

{% for post in site.posts %}
{% capture newyear %}{{ post.date | date: "%Y" }}{% endcapture%}
{% if newyear != year %}
{% if year != "" %}
</ul>
{% endif %}

<h2>{{ newyear }}</h2><ul>

{% assign year = newyear %}
{% endif %}


<time>{{ post.date | date: "%Y-%m-%d" }}</time>
<a href="{{ post.url }}">{{ post.title }}</a>
<br/>
{% endfor %}
</ul>
</ul>


