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

## テーブルに新しい項目を追加したい時
今回は、Usersテーブルにtinyint型のyearを追加する。

```
$ rails g migration AddYearToUsers year:tinyint
```


## Bootstrapを使ったtabの切り替え(tab-pane)

```
<main class="p-3">
  <!-- 3個分のタブ -->
  <ul class="nav nav-tabs">
    <li class="nav-item">
      <a href="#new" class="nav-link active" data-toggle="tab">新着</a>
    </li>
    <li class="nav-item">
      <a href="#popular" class="nav-link" data-toggle="tab">人気</a>
    </li>
    <li class="nav-item">
      <a href="#news" class="nav-link" data-toggle="tab">News</a>
    </li>
  </ul>

 <%# <div class="col mt-4"> %>

<!-- 投稿部分 -->
  <div class="tab-content">
    <div id="new" class="tab-pane active">
   <%# ここから新着 %>
   <div class="card mt-4">
      <%= image_tag 'the-main.jpg', class: "img-fluid" %>
      <div class="card-body">
        <h5 class="card-title">新着投稿</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
      </div>
    </div>

    <div class="card mt-4">
      <%= image_tag 'the-main.jpg', class: "img-fluid" %>
      <div class="card-body">
        <h5 class="card-title">新着投稿2</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
      </div>
    </div>
   <%# ここまで新着 %>
    </div>
    <div id="popular" class="tab-pane">
    <%# ここから人気 %>
    <div class="card mt-4">
      <%= image_tag 'the-main.jpg', class: "img-fluid" %>
      <div class="card-body">
        <h5 class="card-title">人気投稿</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
      </div>
    </div>

    <div class="card mt-4">
      <%= image_tag 'the-main.jpg', class: "img-fluid" %>
      <div class="card-body">
        <h5 class="card-title">人気投稿2</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
      </div>
    </div>
    <%# ここまで人気 %>
    </div>
    <div id="news" class="tab-pane">
    <%# ここからnews %>
    <div class="card mt-4">
      <%= image_tag 'the-main.jpg', class: "img-fluid" %>
      <div class="card-body">
        <h5 class="card-title">ニュース</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
      </div>
    </div>

    <div class="card mt-4">
      <%= image_tag 'the-main.jpg', class: "img-fluid" %>
      <div class="card-body">
        <h5 class="card-title">ニュース2</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
      </div>
    </div>
    <%# ここまでnews %>
    </div>
  </div>
</main>

```
