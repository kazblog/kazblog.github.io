---
layout: page
title: CheatSheet 
permalink: /CheatSheet/
---
同じことを繰り返さない。


<h3>Rails</h3>
{% for post in site.categories.rails-cheatsheet %}
<ul>
<li><a href="{{post.url}}">{{post.title}}</a></li>
</ul>
{% endfor %}
<br>
<br>
<h3>Docker</h3>
{% for post in site.categories.docker-cheatsheet %}
<ul>
<li><a href="{{post.url}}">{{post.title}}</a></li>
</ul>
{% endfor %}
<br>
<br>
<h3>Vue</h3>
{% for post in site.categories.vue-cheatsheet %}
<ul>
<li><a href="{{post.url}}">{{post.title}}</a></li>
</ul>
{% endfor %}
<br>
<br>
<h3>Other</h3>
{% for post in site.categories.other-cheatsheet %}
<ul>
<li><a href="{{post.url}}">{{post.title}}</a></li>
</ul>
{% endfor %}
<br>
<br>