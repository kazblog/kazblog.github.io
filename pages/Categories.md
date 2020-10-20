---
layout: page
title: Categories
permalink: /Categories/
---
<br>
<h2>Rails</h2>
{% for post in site.categories.Rails %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}
<br>

<br>
<h2>JavaScript</h2>
{% for post in site.categories.JavaScript %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}
<br>

<br>
<h2>Vue</h2>
{% for post in site.categories.Vue %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}
<br>

<br>
<h2>Docker</h2>
{% for post in site.categories.Docker %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}
<br>

<!-- <h2>Dev</h2>
{% for post in site.categories.dev %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %} -->
<br>
<h2>Blog</h2>
{% for post in site.categories.blog %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}

















