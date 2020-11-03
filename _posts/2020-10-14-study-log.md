---
layout: post
title:  "Rails ::とassert_no_difference"
date:   2020-10-14 12:39:36 +0900
categories: Rails
permalink: /assert_no_difference/
excerpt_separator: <!--more-->
thumbnail: https://picsum.photos/200/300
---
<!--more-->
### 今日学習して理解したこと2つ
<br><br>
一つ目

#####  ::の記法について。<br>

only: [:edit, :update]<br>

only: :destroy<br>

[]内が一つだけだと、省略して、::と書くことができるのか。<br>

-----------------------------------------------------------------------------------------
二つ目

### assert_no_difference 'User.count' doの挙動
<br><br>



 例えばこの場合。<br>
    assert_no_difference 'User.count' do<br>
      delete user_path(@user)<br>
    end<br>
 <br>
中にある式の実行前後で引数は変わらないかどうか。



<!-- 参考記事[https://qiita.com/knml/items/84c30dc525f43fabf94f](リンク) -->
