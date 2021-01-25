---
layout: post
title:  "RSpecのエラー解決"
categories: cheatsheet
permalink: /rspec-bookmarks
excerpt_separator: <!--more-->
tags: rspec
---

![image here](/assets/img/thumbnail/13.jpeg)

<!--more-->

## Migrations are pending. To resolve this issue, run: bin/rails db:migrate RAILS_ENV=testYou have 27 pending migrations:

```
rails db:migrate:reset
```

↓

## `require': cannot load such file — rails_helper (LoadError)

原因は、このエラーに限らず、そもそもテスト用のDBが作られていなかった。

<br>

'''
rails db:test:prepare
'''

チートシート
rspecのメソッドをmodule化するファイルを作成する方法
https://breakthrough-tech.yuta-u.com/rspec/how-to-make-spec-support/
