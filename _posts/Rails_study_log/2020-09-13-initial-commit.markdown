---
layout: post
title:  "Railsでサービスを作ってみる"
date:   2020-09-13 12:39:36 +0900
categories: Rails_study_log
permalink: :categories/:year/:month/:day/:title/
author: "kaz"
excerpt_separator: <!--more-->
---
<!--more-->
<br>

### はじめに
#### バージョン管理、本番環境は気にせず、<br>「とりあえずRailsに慣れたい」という目的で、<br>今日から作っていきます。


### 環境
・gemやバージョンは、全てRails TutorialをコピペでCloud9を使って作る。<br>
・AWS使わない<br>
・Docker使わない<br>

### 何を作る?

APIを使ったニュースサイト。

### 詳しく

Digital Nomadについてのニュースまとめサイト。リモートワークが増える中、関心が高まりそうなワードだったから。（自分を含めて。）


# さっそく作る
<br>ログイン後のページ<br><br>
![](https://paper-attachments.dropbox.com/s_C204873E5DA45141CA9D22FB309D9D684C5E3FE0EE4510B6E4761DA20E6D7F2B_1599963602352_FireShot+Capture+041+-+manablog-taste+-+127.0.0.1.png)
<br><br>ログインページ<br><br>
![](https://paper-attachments.dropbox.com/s_C204873E5DA45141CA9D22FB309D9D684C5E3FE0EE4510B6E4761DA20E6D7F2B_1599980421939_FireShot+Capture+044+-+Nomad+-+d6195f48b19f4a1c86876c7411c86819.vfs.cloud9.us-east-2.amazonaws.com.png)
<br><br>Aboutページ<br><br>
![](https://paper-attachments.dropbox.com/s_C204873E5DA45141CA9D22FB309D9D684C5E3FE0EE4510B6E4761DA20E6D7F2B_1599982668889_FireShot+Capture+047+-+Nomad+-+d6195f48b19f4a1c86876c7411c86819.vfs.cloud9.us-east-2.amazonaws.com.png)
<br><br>今日はここまで。

### 学んだ事
<!-- <a href="https://webliker.info/html-css/">ワークするかな？</a> -->
[コピーライトの書き方](https://webliker.info/html-css/)<br><br>
[RubyにBotstrapを実装する](https://qiita.com/rhistoba/items/f724dae231d7e28bf477)<br><br>
[HTMLにfontawsomeを実装する](https://cdnjs.com/libraries/font-awesome)<br><br> 
cssがワークしなかったときは、フォルダがscssじゃなかったからかな？Rails Tutorialでも、scssのgemファイルが機能する為には、scssのファイルに書く必要があるって書いてあった。<br>
> Asset Pipeline（[5.2](https://railstutorial.jp/chapters/filling_in_the_layout?version=6.0#sec-sass_and_the_asset_pipeline)）の一部であり、このディレクトリに置かれたスタイルシートは`application.css`の一部としてWebサイトのレイアウトに読み込まれます。さらに、ファイル名の`custom.scss`には`.scss`という拡張子も含まれています。この拡張子は「Sass（Sassy CSS）」と呼ばれるCSSを拡張した言語で、アセットパイプラインはこのファイルの拡張子を見て、Sassを処理できるようにしています（Sassは[5.2.2](https://railstutorial.jp/chapters/filling_in_the_layout?version=6.0#sec-sass)まで登場しませんが、`bootstrap-sass` gemが動作するためのおまじないとして必要です）。
https://railstutorial.jp/chapters/filling_in_the_layout?version=6.0#sec-custom_css



### 感想
RailsTutorialと違って、デザイン、計画を主体的にできるから、コード書いてて楽しい。明日もやる。




<!-- ## あと、記事をループさせる。(飛ばす)

ってことは、さっき作ったhomeページがログイン後のshowページってことか。
↓
ログイン前のhomeページを作る。移動させるとわからなくなるから、これから作る本来のhomeページを下に続けて作って、session#showのrouteとかviewを作った時に、以前作ったブログページを移動させよう。
↓
ホームページ作る。これもjumbtronでいいか。


## showページを作るために、ユーザーのモデルを作成する。

今回は、ユーザーが投稿できるというわけではなく、ピンで保存した記事を閲覧できる専用ページにしようと思う。

知識: 
すでにログイン済みのユーザーページ「signup」を作る。
modelが登場する。

参考資料:

https://railstutorial.jp/chapters/modeling_users?version=6.0#sec-database_migrations -->







