---
layout: page
title: Categories
permalink: /Categories/
---
<br>
<h2>Rails_study_log</h2>
{% for post in site.categories.Rails_study_log %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}
<br>
<h2>Dev</h2>
{% for post in site.categories.dev %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}
<br>
<h2>Blog</h2>
{% for post in site.categories.blog %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}

















