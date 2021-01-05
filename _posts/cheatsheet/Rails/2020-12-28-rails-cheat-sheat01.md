---
layout: post
title:  "Railsチートシート"
date:   2020-12-28 12:39:36 +0900
categories: rails-cheatsheet
permalink: /rails-cheatsheet01
excerpt_separator: <!--more-->
---
![image here](/assets/img/thumbnail/nine.jpeg)
<!-- <div style="text-align: center;">
<img src="/assets/img/thumbnail/nine.jpeg" width="550px" height="400px">
</div> -->
<!--more-->

### restful
https://railstutorial.jp/chapters/sign_up?version=6.0#table-RESTful_users <br>
https://railstutorial.jp/chapters/user_microposts?version=6.0#code-microposts_resource


### userとpostをrelationでつなぐ。
https://railstutorial.jp/chapters/following_users?version=6.0#fig-user_has_many_following
https://railstutorial.jp/chapters/following_users?version=6.0#fig-user_has_many_followers

##userとpostの関係メソッドチェーン。
https://railstutorial.jp/chapters/user_microposts?version=6.0#table-association_methods

## followingとrelationshipとuserのメソッドチェーン
https://railstutorial.jp/chapters/following_users?version=6.0#table-association_methods_relationships


## memberメソッドを使ったfollowingのメソッドチェーン
https://railstutorial.jp/chapters/following_users?version=6.0#table-following_routes


## railsのDBリセット&再構築

```
$ rails db:migrate:reset
$ rails db:seed
```


## Bootstrapを使ったtabの切り替え

```
<main class="p-3">
  <!-- 4個分のタブ -->
  <ul class="nav nav-tabs">
    <li class="nav-item">
      <a href="#photo1" class="nav-link active" data-toggle="tab">タブ１</a>
    </li>
    <li class="nav-item">
      <a href="#photo2" class="nav-link" data-toggle="tab">タブ2</a>
    </li>
    <li class="nav-item">
      <a href="#photo3" class="nav-link" data-toggle="tab">タブ3</a>
    </li>
    <li class="nav-item">
      <a href="#photo4" class="nav-link" data-toggle="tab">タブ4</a>
    </li>
  </ul>

  <!-- 写真部分 -->
  <div class="tab-content">
    <div id="photo1" class="tab-pane active">
      <img src="images/photo1.jpg" class="img-fluid" alt=""/>
    </div>
    <div id="photo2" class="tab-pane">
      <img src="images/photo2.jpg" class="img-fluid" alt=""/>
    </div>
    <div id="photo3" class="tab-pane">
      <img src="images/photo3.jpg" class="img-fluid" alt=""/>
    </div>
    <div id="photo4" class="tab-pane">
      <img src="images/photo4.jpg" class="img-fluid" alt=""/>
    </div>
  </div>
</main>
```
