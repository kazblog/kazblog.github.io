---
layout: post
title:  "method: :get, :postについて"
date:   2021-01-15 12:39:36 +0900
categories:  computer
permalink: /untitled
excerpt_separator: <!--more-->
tags: rails, computer
---

<!--more-->
method: :getとは何を意味したいるのか。

これもget

```ruby
<%= form_tag posts_path, method: :get, class: 'nav justify-content-cente' do %>
      <%= select_tag :tag_id,
                     options_from_collection_for_select(Tag.all, :id, :name, params[:tag_id]),
                     {
                       prompt: 'カテゴリー',
                       onchange: 'submit(this.form);',
                       class: 'form-control'
                     }
      %>
    <% end %>

<p>検索</p>
<%= form_tag(search_path,:method => 'get') do %>
  <%= text_field_tag :search %>
  <%= submit_tag 'Search', :name => nil %>
<% end %>
```

ユーザーが情報を送信してそれを受け取るから？

これはpost

```ruby
<%= link_to favorites_path(post_id: @post.id), method: :post do %>
```

これは、こっちが定めた値をユーザーが送信したから？

↓

getは、urlの後にパラメーターを付与して表示される。

get: そのページ下さい

post: このデータあげます。

get: 保存しない,すでにあるページを差し出す。

post: DBに保存

get と form_tagは密接に関係している。

form_tag：modelに基づかないformを作る際に用いる

form_tagはDBの変更に関わらない

参考:

[https://qiita.com/ryokky59/items/bba97cbfaa899b03e071](https://qiita.com/ryokky59/items/bba97cbfaa899b03e071)

---

DBにテーブルを格納していなくても、getではparamsを使うことができる。
