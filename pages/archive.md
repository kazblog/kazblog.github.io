---
layout: page
title: Archive
permalink: /archive/
---
<br>
<h1>Dev</h1>
{% for post in site.categories.dev %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}
<br>
<h1>Blog</h1>
{% for post in site.categories.blog %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}
-------------------------------
{% for post in site.posts %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}

<br>
{% for post in site.pages %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}
















