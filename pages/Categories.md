---
layout: page
title: Categories 
permalink: /categories/
---




<h3><i class="fas fa-tag"></i> Rails</h3>
{% for post in site.tags.rails %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}
<br>
<br>

<h3><i class="fas fa-tag"></i> RSpec</h3>
{% for post in site.tags.rspec %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}
<br>
<br>

<h3><i class="fas fa-tag"></i> Docker</h3>
{% for post in site.tags.docker %}
<a href="{{post.url}}">{{post.title}}</a>
{% endfor %}
<br>
<br>



<h3>ブックマーク</h3>
{% for post in site.categories.cheatsheet %}
<ul>
<li><a href="{{post.url}}">{{post.title}}</a></li>
</ul>
{% endfor %}
<br>
<br> 

<!-- <h3>Other</h3>
{% for post in site.categories.other-cheatsheet %}
<ul>
<li><a href="{{post.url}}">{{post.title}}</a></li>
</ul>
{% endfor %}
<br>
<br> -->


<!-- <h3>チートシート</h3>
{% for post in site.categories.Cheat %}
<ul>
<li><a href="{{post.url}}">{{post.title}}</a></li>
</ul>
{% endfor %}
<br>
<br>


<h3>Railsに関する記事</h3>
{% for post in site.categories.Rails %}
<ul>
<li><a href="{{post.url}}">{{post.title}}</a></li>
</ul>
{% endfor %}
<br>

<br>
<h3>JavaScriptに関する記事</h3>
{% for post in site.categories.JavaScript %}
<ul>
<li><a href="{{post.url}}">{{post.title}}</a></li>
</ul>
{% endfor %}
<br>

<br>
<h3>Vueに関する記事</h3>
{% for post in site.categories.Vue %}
<ul>
<li><a href="{{post.url}}">{{post.title}}</a></li>
</ul>
{% endfor %}
<br>

<br>

<br>
<h3>環境構築に関する記事</h3>
{% for post in site.categories.Built-environment %}
<ul>
<li><a href="{{post.url}}">{{post.title}}</a></li>
</ul>
{% endfor %}
<br>
<br> -->


















