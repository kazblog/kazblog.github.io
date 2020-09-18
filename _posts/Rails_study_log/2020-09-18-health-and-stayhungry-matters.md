---
layout: post
title:  "睡眠と少食が集中を助ける"
date:   2020-09-18 12:39:36 +0900
categories: Rails_study_log
permalink: :categories/:year/:month/:day/:title/
author: "kaz"
excerpt_separator: <!--more-->
---

<!--more-->

感想:
今日は集中できなかったな。原因は、「寝不足」「食べ過ぎ」「クーラーつけずにやっていたから、暑くて集中できなかった。」プログラムを書き始めてから、深い集中が必要になった。そう言う時に、「空腹」「健康」は最強に集中することを助けるとだんだん経験からわかってきた。こう言う大切なことを忘れないように、毎日見る場所に書いておこうと思う。

あと、明日はDockerをインストール時にdamonのエラーを直そうと思う。


----------
# 以下今日のlog


# JS(ES6)の必要性を知る。
https://qiita.com/hisamura333/items/e3ea6ae549eb09b7efb9


なんか、彼は、railsでは面倒なことを、JSで代用していたらしい。(非同期/ajax)

https://cr-vue.mio3io.com/

https://www.youtube.com/watch?v=pnsieVYy72M&&list=PLpYVzO5BZomqbLjRiHo7VvVYotX9QoQ0N&index=2&t=0s


[https://youtu.be/pnsieVYy72M?t=0s](https://youtu.be/pnsieVYy72M?t=0s)


学んだこと
・サーバーから返されるのは、HTMLファイル。(昔は。今もそうだが。)
・クリックすると、再レンダリングされる、全てのページが再読み込みされる(昔は。今もそうだが)
今は、もっとリッチなテキストを返してくれる
↓
キーワード: ajax(非同期通信)

## ちょっとの画面の変更で、全てのページが再レンダリングされるのは、ちょっと効率が悪い。だから、ページが更新されずに、変更したそこだけが変わるようにしたい。それを可能にするのが、AJAX。
(例: Twitterのいいねは、いいねだけ更新されている。)
↓
ajaxが加わると、どんなやりとりがクライアントとサーバで実現するんだろう。（以前はHTMLファイルだけ。）
↓
まあ普段は、htmlと.jsファイルが返ってくる。
そして、クライアントがサーバーを更新したら、JSONと呼ばれる、ただのデータが返ってくる。(.jsから)
↓
ってことは、HTMLはそのままクライアント側にいて、JSONだけが返ってくるイメージかな？


JS使うと、headerとfooterはそのままで、mainだけ再レンダリングするという技術が実現できる。


----------
# Rails Tutorial


      <%= debug(params) if Rails.env.development? %>

これだけで、開発環境のみデバックを表示させることができるなんて楽だなー。
ちなみにtest, development, productionがある。


----------

ニュースサイトって、ログインしたら、ユーザーはなんの権限が与えられるんだろう。

・その人に特化したニュースサイトだな。
・ピンできる

とりあえず必要最低限でいいから、ログインしても変わらないと言う機能で行こう。

----------


# Rails parse json 



https://qiita.com/vzvu3k6k/items/dd45ad293ae2d60c7a4e


https://www.google.com/search?rlz=1CDGOYI_enJP861JP861&hl=en-US&sxsrf=ALeKk00rdg6kvL_kDT5izbxYRzfq8wCGyg%3A1600406582382&ei=NkRkX9DQFprZ-QaXj5uwCQ&q=ruby+parse+%E3%81%A8%E3%81%AF&oq=ruby+parse+%E3%81%A8%E3%81%AF&gs_lcp=ChNtb2JpbGUtZ3dzLXdpei1zZXJwEAMyBQgAEM0COgQIABBHOgQIABBDOgIIADoECCMQJzoHCAAQFBCHAjoGCAAQBBAeOggIABAIEAQQHlD2qQVYpdsFYK_dBWgCcAJ4AIABzgKIAcUGkgEHMi4zLjAuMZgBAKABAcgBCMABAQ&sclient=mobile-gws-wiz-serp#



https://stackoverflow.com/questions/5410682/parsing-a-json-string-in-ruby




https://qiita.com/tsubasa_hiroe/items/8ba36f41414a254621ef



https://www.sejuku.net/blog/16196


https://uxmilk.jp/13387


https://riptutorial.com/ruby/example/20606/using-json-with-ruby


https://www.tutorialspoint.com/json/json_ruby_example.htm



https://temboo.com/ruby/parsing-json




https://medium.com/@pawlkris/unlocking-the-power-of-parsing-json-in-ruby-a02f350f2db1


https://ruby-lang.co/read-json-file/





割と共通しているもの書き方はここに詰まっている。

https://qiita.com/tsubasa_hiroe/items/8ba36f41414a254621ef



https://qiita.com/awakia/items/bd8c1385115df27c15fa


まあ、またここを見るか。まだ観てないけど、体系的。だし、一応見て見る。ゆっくり進もう。

https://www.youtube.com/watch?v=GZvSYJDk-us&&feature=youtu.be


[https://youtu.be/GZvSYJDk-us](https://youtu.be/GZvSYJDk-us)




----------
# Docker


https://www.youtube.com/watch?v=fqMOX6JJhGo&&feature=youtu.be


[https://youtu.be/fqMOX6JJhGo](https://youtu.be/fqMOX6JJhGo)

学んだ事
今までは、全てが一つだと思っていた。が、思い出した。一つのプロセスで、一つのコンテナだから、プログラミング言語、DBなど、それぞれが独立しているコンテナに入っている。と言うイメージ。




