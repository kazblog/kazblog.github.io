---
layout: post
title:  "Railsでview数を実装する"
categories: rails
permalink: /rails-view-rank
excerpt_separator: <!--more-->
tags: rails
---

<!--more-->

前提

gem impressionistインストールしている

gem kaminariをインストールしている

達成すること

投稿へのアクセス数が多い順に並べることにする

post.rb

```ruby
is_impressionable counter_cache: true
```

controller

```ruby
posts_get_views = Post.order(impressions_count: 'DESC')
@posts_get_views = Kaminari.paginate_array(posts_get_views).page(params[:page]).per(4)
```

rails c で　Post.order(impressions_count: 'DESC')

```ruby
[10] pry(main)> Post.order(impressions_count: 'DESC')
=>   Post Load (3.9ms)  SELECT `posts`.* FROM `posts` ORDER BY `posts`.`impressions_count` DESC
[#<Post:0x00005621c1a62960
  id: 24,
  content:
   "#転職 udin id mrisLorem #ワーキングホリデー ipsum dolor sit amet, consectetur adipiscing elit. Phasellus magna enim, tempus tristique dignissim sit amet, iaculis in nibh. Vestibulum sed neque nibh. Morbi augue nunc, interdum quis nunc sit amet, auctor dignissim neque. Nunc mi eros, vehicula molestie mollis in, porta vitae nulla. Sed in lobortis arcu. Nullam ante purus, tincidunt sit amet eros ut, dignissim pellentesque lectus. Proin semper vestibulum lacus, quis hendrerit turpis venenatis in. Vivamus vel porta augue. Integer quis ullamcorper ex. Nunc lacinia arcu et justo pretium, ut porttitor neque feugiat. Maecenas facilisis consectetur metus sit amet imperdiet. Nullam vel felis dapibus, accumsan purus sed, pretium massa. Nullam condimentum augue eget lectus blandit, sit amet elementum elit tincidunt. Aliquam ac tellus diam. Nullam dignissim tempus est, non vulputate nisi egestas ultricies.da. Duis efficitur sem sed sagittis convallis.",
  user_id: 1,
  created_at: Sun, 31 Jan 2021 08:28:26.434149000 UTC +00:00,
  updated_at: Sun, 31 Jan 2021 08:28:26.434149000 UTC +00:00,
  title: "いじん",
  tag: nil,
  image: "post-img02.jpg",
  covid: "コロナ後",
  impressions_count: 15>,
 #<Post:0x00005621c1a62708
  id: 12,
  content:
```

この定義で間違っていなかったことが確認できた。

view

```ruby
<% @posts_get_views.each do |post_get_views| %>
 <%= post_get_views.title %>
<% end %>
<%= paginate @posts_get_views %>
```

完成

参考

[【Rails】impressionistを用いてPV数ランキングの実装 - Qiita](https://qiita.com/matsubishi5/items/bec2040f766fc7b079a0)
