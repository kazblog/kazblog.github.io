---
layout: post
title:  "APIでスタックした。もっと体系的に学ぶ必要がある。"
date:   2020-09-17 12:39:36 +0900
categories: Rails_study_log
permalink: :categories/:year/:month/:day/:title/
author: "kaz"
excerpt_separator: <!--more-->
---
<!--more-->

目標: APIを徹底的に理解して、APIを実装する。<br><br>

感想: APIの叩き方は、それぞれのサービスによって違う。REST APIの教材はグーグルにたくさんあるんだけど、apiを叩く方は少ないというか、「もうこいう前提条件はわかってますよね」みたいなことから始まるので、自分はその前提条件がわからず詰まるという流れ。でもなんどもググっていると、パズルのピースが埋まっていっているような感覚はあるから、このままググり続けたい。


----------

# 以下は、今日学習したAPIについてのlog


https://qiita.com/NagaokaKenichi/items/df4c8455ab527aeacf02

> APIの機能はわかっているけれども、その中身の実際の動作は詳しくわからない(知らなくてもよい)機能の塊を、外部から呼び出す仕様のことを指す。


![](https://paper-attachments.dropbox.com/s_6D6B7033CBD2CBE65C91A245E44FDA1704C1C59604A356E21025B5F7B0DEBA73_1600307486605_image.png)



> 上記図の右側の「呼ばれる側のシステム」そのものをWeb APIと呼ぶこともある。


APIを公開することで、収益を上げたりすることができる。amazonのアフェリとかまさにAPI成功例であり、彼らが初期のAPI活用企業。

TikTokのコラボ機能を有効にすることは、そのアカウント保有者がAPIを提供していると言えるかもしれないかもしれない。

webAPIはたくさんアクセスされると、サーバーがダウンしてしまう可能性がある。　もし、外部のサービスがたくさんなくセスを必要とするなら、有料にしたりする。

ここまでわかったこと。
APIはつまりオープンソースで、自分一人の機能ではなく、シェアすることで収益も上がるし、自分たちでは想像もしなかったサービスを作ってくれる。



----------


https://qiita.com/busyoumono99/items/9b5ffd35dd521bafce47


なるほど。APIを作る,APIを利用する。この言葉が欲しかった。


## 前提知識

アプリケーションの種類

- スタンドアローン(ネットワークが必要ない。Wordとか)
- クライアントサーバ(インターネット)
- 

レストランの伝票がhttp


----------
# APIとは
##  ・関数
## ・特定の機能を持つプログラム部品


# WebAPIとは
> ネットワーク越しに利用できる関数。URLが関数名で引数を渡す事で結果が変化する。

確かに。weather_app作った時に


> Webサイトに外部のサイトの提供する機能や情報を組み込んだり、アプリケーションソフトからWeb上で公開されている機能や情報を利用する際などに用いられる。


> WebAPIを実行する事をWebAPIを叩くという言い回しがある。

外部APIを使いたいときは、ググる時に「WebAPI」と入力すればいいのか。「WebAPI　叩く」



![](https://paper-attachments.dropbox.com/s_6D6B7033CBD2CBE65C91A245E44FDA1704C1C59604A356E21025B5F7B0DEBA73_1600311612778_image.png)


[参考](https://www.atmarkit.co.jp/ait/articles/0703/13/news095_2.html)

ネットサーフィンとWebAPIは似ている。

いい説明
**サーバーで用意している関数(webAPI)をhttp通信して利用すること。**


http://zipcloud.ibsnet.co.jp/api/search?zipcode=2130001

URL.zipcode(2130001)



----------

キタミ式のP.225よりAPIの説明あり。
アプリケーション(応用ソフトウェア)→OS(基本ソフトウェア)→ハードウェア

アプリケーションからは、ハードウェアが見えない。ただ、OSは見える。全てのOSの中身は見えないが、「こうすればこう動く」という説明書は見える。それがAPI






----------





# それぞれのAPIでコードの書き方が違う。何か共通の描き方っていうのはあるはずだ。それを学べるのは、体系的に学ぶしかない。だから
https://www.youtube.com/watch?v=GZvSYJDk-us&


[https://youtu.be/GZvSYJDk-us](https://youtu.be/GZvSYJDk-us)

と

https://www.youtube.com/watch?v=7YcW25PHnAA&


[https://youtu.be/7YcW25PHnAA](https://youtu.be/7YcW25PHnAA)
をみてみよう。

コード取ってきてひょいじゃダメだ。わからなすぎるから、体系的に。




----------
# 以下は、Rails Tutorialのlog


## セキュアなパスワードを実装する

ユーザーの認証は
パスワードの送信、
ハッシュ化、(password_digest)
データベース内のハッシュ化された値との比較、(authenticate)
という手順で進んでいきます。

実は、has_secure_passwordでほとんどの実装が終わってしまう。


    $ rails generate migration add_password_digest_to_users password_digest:string



    gem 'bcrypt',         '3.1.13'

↑ハッシュ関数を使う時に、このgemが必要。
















----------

ちょっと思ったこと
もしわからなかったら、めっちゃ有名なAPIをやる。そしたら解説サイトがあるから。
あと、APIってそれぞれのサイトに独自のルールがあるっぽい。

----------

# 以下はAPIの学習素材

やりたいことに近いサイト

これはgoogle map

https://www.sejuku.net/blog/116580

https://rapidapi.com/blog/news-api-ruby-on-rails/


↑エラーが出てわからん。てかこれに得意になっても、rapidAPIがうまくなるわけで、APIを学べるわけではない。



https://www.youtube.com/watch?v=TbN0JpVoHaA&


[https://youtu.be/TbN0JpVoHa](https://youtu.be/TbN0JpVoHaA)

http://smsurf.app-rox.com/api/


ここにもリンクある。
https://kazumawada.github.io/rails_study_log/2020/09/16/mede-first-api-app/


https://www.youtube.com/watch?v=fqMOX6JJhGo&


[https://youtu.be/fqMOX6JJhGo](https://youtu.be/fqMOX6JJhGo)


今日の記事Twitterにアウトプット。全部見れなかったら、明日に持ち越し。

https://qiita.com/rana_kualu/items/27c883922061c33af0a4

https://qiita.com/freddi_/items/fe8e878187f315d80d87

https://qiita.com/Hassan/items/134009209f5709f892b1

https://qiita.com/yamken/items/a9db6b07142ca8bfd19e

https://qiita.com/megumu-u/items/73b728ad1d381717d731

https://jp.techcrunch.com/2020/09/16/2020-09-15-dropbox-ceo-drew-houston-says-the-pandemic-forced-the-company-to-reevaluate-the-product-roadmap/?guccounter=1&guce_referrer=aHR0cHM6Ly90LmNvL3pkaGZkaEd1Qjc_NQ&guce_referrer_sig=AQAAAK1RMx5_IA5dth1wapUDK77VROSBRYEN9iHw8QQuV1GeIiQX_1QJYW_c3wYGTuoHDEOKtQnwPLdOAFceRKoAlVzzsFXOUwKXV56bGfgQFj5iHRgEB0RdKfkpks-IbWSySmOQwHh3iGvM7XhJiMVfOgp3TVa0nFavViENBS35ZuP7

https://qiita.com/S-nobol/items/a9a2b5aa3b80060bb511?utm_content=buffer45777&utm_medium=social&utm_source=twitter.com&utm_campaign=buffer

https://qiita.com/hirokidaichi/items/27c757d92b6915e8ecf7



