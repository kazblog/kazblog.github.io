---
layout: post
title:  "検索機能実装で学んだこと"
date:   2021-01-23 12:39:36 +0900
categories: rails
permalink: /rails-search
excerpt_separator: <!--more-->
tags: rails
---

<!--more-->
searchを実装する時に使用するコードを理解してみる。

・post.rb

```ruby

def self.search(search)
      if search
        Post.where(['content LIKE ?', "%#{search}%"])
      else
        Post.all
      end
end

```

・controller

```ruby
 def search
   @posts = Post.search(params[:search])
 end
```

・view

```ruby
<p>検索</p>
<%= form_tag(search_path,:method => 'get') do %>
  <%= text_field_tag :search %>
  <%= submit_tag 'Search', :name => nil %>
<% end %>



 <% @posts.each do |p| %>
 
　　省略   
　　
  <% end %>
```

上のコードを理解していく。

↓

Like: あいまい検索

```ruby
モデルクラス.where("カラム名 LIKE?", "検索したい文字列")

ex,
User.where("name LIKE?", "%あ%")
```

この書き方だと、あるモデルのcontentカラムの文字列データのどこかの部分に「こんにちは」と含まれているレコードを抽出できる。

```ruby
 Post.where(['content LIKE ?', "%#{search}%"])
```

このcontentは、何を指しているのか。
↓
カラム。

titleカラムもヒットするようにしたい。

複数のカラムから参照したい時は、これでワークした。

```ruby
Post.where(["content LIKE ? or title Like ?", "%#{search}%", "%#{search}%"])
```

searchを同じ数書かないと、argument errorになるから注意。

参考:

[https://qiita.com/seri1234/items/765423c2c46ca4114da0](https://qiita.com/seri1234/items/765423c2c46ca4114da0)

[https://pikawaka.com/rails/where](https://pikawaka.com/rails/where)



