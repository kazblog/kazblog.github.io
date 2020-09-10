---
layout: page
title: Archive
permalink: /archive/
---

{% for post in site.posts %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}

<br>
{% for post in site.pages %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}

<br>
<h1>Blog</h1>
{% for post in site.categories.blog %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}


<br>
<h1>Dev</h1>
{% for post in site.categories.dev %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}

<br>
<h1>asserts</h1>
{% for file in site.static_files %}
<a href="{{post.url}}"></a>
{{file.path}}
{% endfor %}

<br>
<h1>asserts name</h1>
{% for file in site.static_files %}
{{file.name}}
{% endfor %}












<br>
<h1>img</h1>
{% for file in site.static_files %}
{% if file.image %}
<img src="{{file.path}}" alt="">
{% endif %}
{% endfor %}