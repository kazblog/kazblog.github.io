---
layout: page
title: Categories
permalink: /Categories/
---
<br>
<h3>Built-environment</h3>
{% for post in site.categories.Built-environment %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}
<br>
<br>
<h3>Rails</h3>
{% for post in site.categories.Rails %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}
<br>

<br>
<h3>JavaScript</h3>
{% for post in site.categories.JavaScript %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}
<br>

<br>
<h3>Vue</h3>
{% for post in site.categories.Vue %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}
<br>

<br>


<!-- <h2>Dev</h2>
{% for post in site.categories.dev %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %} -->

<!-- <h2>Blog</h2>
{% for post in site.categories.blog %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %} -->

















