---
layout: page
title: Categories
permalink: /Categories/
---
<br>
<h3>Built-environment</h3>
{% for post in site.categories.Built-environment %}
<ul>
<li><a href="{{post.url}}">{{post.title}}</a></li>
</ul>
{% endfor %}
<br>
<br>


<h3>Rails</h3>
{% for post in site.categories.Rails %}
<ul>
<li><a href="{{post.url}}">{{post.title}}</a></li>
</ul>
{% endfor %}
<br>

<br>
<h3>JavaScript</h3>
{% for post in site.categories.JavaScript %}
<ul>
<li><a href="{{post.url}}">{{post.title}}</a></li>
</ul>
{% endfor %}
<br>

<br>
<h3>Vue</h3>
{% for post in site.categories.Vue %}
<ul>
<li><a href="{{post.url}}">{{post.title}}</a></li>
</ul>
{% endfor %}
<br>

<br>


















