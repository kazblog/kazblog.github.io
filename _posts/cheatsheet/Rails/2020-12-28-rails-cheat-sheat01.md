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

その逆。カラム削除

```
rails g migration RemoveYearFromUsers year:tinyint 
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

## どうcontrollerに定義していいかわからない時の解決法

 # 追加
    def open
        binding.pry
    end

    private

    # paramsから欲しいデータのみ抽出
    def post_params
        params.require(:post).permit(:name, :title, :content)
    end
end
# サービス確認
$ docker ps     
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                               NAMES
59b9c55d27f6        posts_webserver     "bundle exec rails s…"   32 minutes ago      Up 14 minutes       0.0.0.0:3000->3000/tcp              posts_webserver_1
054877397d5e        jenkins:2.60.3      "/bin/tini -- /usr/l…"   4 days ago          Up 14 minutes       0.0.0.0:8080->8080/tcp, 50000/tcp   posts_jenkins_1
c6088fba0e5e        mysql:5.7           "docker-entrypoint.s…"   4 days ago          Up 14 minutes       3306/tcp                            posts_db_1

# デバッグモード
$ docker attach posts_webserver_1

# web上で、http://localhost:3000/posts/1 にアクセス
From: /app/app/controllers/posts_controller.rb @ line 22 PostsController#open:

    20: def open
    21:     binding.pry
 => 22: end

[1] pry(#<PostsController>)> params[:id]
=> "1"
Controller の open メソッドに binding.pry を仕込み、デバッ
  
  
  ## link_toの囲い方
  
  link_toメソッド
結論から言うと、カッコつき link_to の後ろに do をつけて、 閉じ end で、ブロックを囲める。

<%= link_to(item_path(item), class: 'list-content') do %>
  <div class="content">
    <div class="inner-left">
      ...
    </div>
    <div class="inner-right">
      ...
    </div>
  </div>
<% end %>
