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

## `require': cannot load such file — rails_helper (LoadError)

原因は、このエラーに限らず、そもそもテスト用のDBが作られていなかった。

'''
rails db:test:prepare
'''

チートシート
rspecのメソッドをmodule化するファイルを作成する方法
https://breakthrough-tech.yuta-u.com/rspec/how-to-make-spec-support/
