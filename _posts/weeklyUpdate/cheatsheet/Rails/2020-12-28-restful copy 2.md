---
layout: post
title:  "RailsのError解決集"
date:   2020-12-28 12:39:36 +0900
categories: rails-cheatsheet
permalink: /rails-error
excerpt_separator: <!--more-->
---
![image here](/assets/img/thumbnail/eight.jpeg)
<!--more-->
### Webpacker::Manifest::MissingEntryError in Test#home

```
rails webpacker:install
```

<hr>

### Could not find bson-4.4.2 in any of the sources Run bundle install to install missing gems.

```
docker-compose build --no-cache
or
docker-compose run web bundle install
```
↓
<br>
docker-compose dowm, up 

[参考](https://fuqda.hatenablog.com/entry/2019/03/21/204118)

<hr>