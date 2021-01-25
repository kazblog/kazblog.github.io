---
layout: post
title:  "RSpecの基本的な書き方"
date:   2021-01-25 12:39:36 +0900
categories: rspec rails
permalink: /rspec-basic-syntax
excerpt_separator: <!--more-->
tags: rails rspec
---

<!--more-->

RSpecのfill_inの書き方

```ruby
perform_enqueued_jobs do
      expect { 
        fill_in "user_name", with: "testname"
        fill_in "user_password", with: "test_password"
        fill_in "user_password_confirmation", with: "test_password"
        select "1年", from: "user_year"
        fill_in "user_bio", with: "hello"
        click_button "アカウント作成"
      }.to change(User, :count).by(0)
  end
```

・fill_inにmodel_ラベル名, withにユーザーが入力するであろう文字列。

select_tagは他と書き方が違うので注意。
