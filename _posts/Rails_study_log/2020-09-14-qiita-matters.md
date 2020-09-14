---
layout: post
title:  "qiita-matters"
date:   2020-09-14 12:39:36 +0900
categories: Rails_study_log
permalink: :categories/:year/:month/:day/:title/
author: "kaz"
excerpt_separator: <!--more-->
---

ググるならまずqiitaだと知った日
<!--more-->

<br>
昨日の反省 
<br>
ページのスクリーンショットを載せるのではなく、エンジニアエンジニアらしくコードで残した方がいいと思う。

# はじめに
昨日は、頭の中で次どうするか考えながらコードを書いていた。それだと一度に頭の中で処理するものが多すぎて、要領が悪い。だから、今回は計画をここに一度書いてから、コードを書き始めることにする。


# 今日実装するもの
- 新たにUserモデルを作る。
- APIを叩く。


# さっそく作る


## 新たにUserモデルを作る。

ユーザー登録で最初にやることは、ユーザーの受け皿を作ること。つまりModelとDB。
emailとnameをstringで作っていく。


## 有効性
      def setup
        @user = User.new(name: "Example User", email: "user@example.com")
      end
    
      test "should be valid" do
        assert @user.valid?
      end
## 存在性
    test "name should be present" do
        @user.name = "     "
        assert_not @user.valid?
      end


    validates :name, presence: true
    #こうもかける
    validates(:name, presence: true)

長さを検証
51文字以上だとerror(red)

    test "name should not be too long" do
        @user.name = "a" * 51
        assert_not @user.valid?
    end

244文字以上だとerror(red)

      test "email should not be too long" do
        @user.email = "a" * 244 + "@example.com"
        assert_not @user.valid?
      end

実装(さっきの存在性と合わせて)(green)

    validates :name,  presence: true, length: { maximum: 50 }
    validates :email, presence: true, length: { maximum: 255 }

フォーマットのテストもあるが、今回は飛ばす
次回参考:　https://railstutorial.jp/chapters/modeling_users?version=6.0#sec-format_validation


## 一意性

→他に同じデータがない。
validatesメソッドの:uniquenessオプションを使います。

まず、重複したメールアドレスがないか。RED

    test "email addresses should be unique" do
        duplicate_user = @user.dup
        @user.save
        assert_not duplicate_user.valid?
      end

dupは、同じ属性を持つデータを複製するためのメソッドです。

dupで複製させる
↓
一つをsave
↓
もう一つはnot validだよね？

GREEN

     uniqueness: true

(ここ↓イマイチ理解できていない。https://railstutorial.jp/chapters/modeling_users?version=6.0#code-validates_uniqueness_of_email_case_insensitive_test)

    duplicate_user.email = @user.email.upcase
    #大文字小文字を統一するために、まず大文字にする。
    @user.save

GREEN

    uniqueness: { case_sensitive: false }

ここまで一意性を実装してきたが、まだActive RecordはDBのレベルでは一意性を保証してないらしい。
                                                                 ↓

> この問題はデータベースレベルでも一意性を強制するだけで解決します。
> 

how?


> 具体的にはデータベース上のemailのカラムにインデックス（index）を追加し、そのインデックスが一意であるようにすれば解決します

データベースのemailにindexを追加し、それが一意であればok。


    $ rails generate migration add_index_to_users_email

生成されたファイル　db/migrate/20200914015650_add_index_to_users_email.rb


    class AddIndexToUsersEmail < ActiveRecord::Migration[6.0]
      def change
        add_index :users, :email, unique: true
      end
    end

user, emailの一意性をtrue。

    add_index :users, :email, unique: true

fixtureを消したらGREEN

まだ問題が。
Foo@ExAMPle.Comとfoo@example.comが別々の文字列だと解釈してしまうデータベースがある。
これらの文字列は同じだと認識させたい。

how?

「データベースに保存される直前にすべての文字列を小文字に変換する」という対策を採ります。
例えば、Foo@ExAMPle.Comは保存する直前にfoo@example.comに変換する。

Active Recordのコールバックを使う。(ある特定の時点で呼び出される)
今回は、before_saveと言うコールバックを使う。これで、ユーザーを保存する前に、大文字を小文字に変換させます。

    before_save { self.email = email.downcase }

続き

https://railstutorial.jp/chapters/modeling_users?version=6.0#code-email_downcase_test



飽きてきたから、APIを叩こうと思う。

# API

調べる
「APIを自分のプログラムに取り込める」と言うことは知っているが、具体的にどこからどうやって取得して、どう自分のプログラムに反映させるのかわからないから、それを調べる。
[気をつけること](https://webtan.impress.co.jp/u/2019/07/01/33188)


## GoogleAPIsについて

[googleAPIs](https://codezine.jp/article/detail/7977)を扱えれば、どんなAPIも扱えるようになるのかな？

基本的に、今のAPIは、JSONで取得できるようになっている。このAPIを、Discovery based APIと言う。そしてこのAPIは, Google APIs Discovery Serviceという、「APIを探すAPI」を使って探すことができます。
↓
Google APIs Discovery Serviceを使って、Discovery based API（JSON方式）を取得する。
Google API Explorerは、Google APIs Discovery Serviceを使ってAPIを取得し、実行できる。


## Google APIは、RESTに似た構造で作られている。

get, patch, delete, updateとか。

,,,,これってgoogleのサービスを使える(gmailとか)もので、google検索した他人のブログのAPIは取ってこれないのかも。

## APIには種類がある
- webサービス向けのAPI

「個人が使用するWebサービス」のリソースに対するアクセスが提供されます。(特定のユーザが所有するリソースを操作できます。)

- プラットフォーム向けのAPI
- Google app向けのAPI

googlrのリソースを、企業へ渡す。

今回は、webサービス向けAPIが当てはまりそう。


# RSS


## RSSとAPIの違いは？

今の所
RSSは、情報をまとめてくれるが、プログラムに書けるのかな？
APIは
こんな時は[stackOverflow](https://stackoverflow.com/questions/28061118/difference-between-rss-and-web-api)。

> We will be using RSS as broadcasting channel, who ever wants to know what's happning in my Company can follow my company website's RSS feed.

RSSはノンプログラマーでも簡単にアクセスできる購読サービスみたいな感じで、APIが認証が必要でプログラムで自分のサービスで観れるものかな。
ってことは、RSSをいくら取得しても、自分が作ったプログラムには取り入れることはできないのか。。

ググって見る言葉を変えて見る
「キュレーションサービス rails」とか。
結果。
そう。[こんな感じのサイト](https://menthas.com/)を作りたいんだよな。アルゴリズムとかめっちゃむずそう。
本当にRSSを自分のサービスに埋め込むことはできないのか？
もう一度調べて見る。
konosaitodeha
[このサイト](https://www.buildinsider.net/language/rubytips/0016)では、RSSをrubyに組み込んでサイトで表示している。

、、APIとRSS何が違うの？どっちもRailsに入るじゃん。

## RSS, APIの違いがわからなくなってきたので、もう一回調べる。


- API:　約束事。こうやれば、こういった情報が帰ってきますよ。
- web API:　URLで表示したい情報を操作できる。(XML, JSON)


- スクレイピング　とAPIも違うのか。一緒だと思ってた。

↓
APIを提供していなかったら、スクレイピングを利用する。
もっと詳しく
API:　情報を提供している証拠。各API提供者によってフォーマットが異なっていたり、欲しい情報がAPIでは提供されていないということもある。


よく見るwifiマークのRSS。それもxmlで返してくれる。
これか。
https://news.google.com/rss?hl=en-US&gl=US&ceid=US:en
解説はこれか。

https://wa3.i-3-i.info/word1582.html

> ホームページやブログの目次・更新案内用に調整されたXML


## rssとは？(Really Simple Syndication)

複数のウェブサイトを、ひとまとめにして見やすくしたもの。
**RSSを**[**Feedy**](https://feedly.com/i/welcome)**で読むって感じ。**だから、FeedyはRSS reader。
参考: [この動画](https://www.youtube.com/watch?v=6HNUqDL-pI8)

## 取得したRSSたち

google newで「Digital Nomad」についての記事を取ってこれた。
https://news.google.com/rss/search?q=%7Bdigital+nomad%7D&hl=en-US&gl=US&ceid=US:en

「Nomad」について。
https://news.google.com/rss/search?q=%7BNomad%7D&hl=en-US&gl=US&ceid=US:en

remote work について
https://news.google.com/rss/search?q=%7Bremote%20work%7D&hl=en-US&gl=US&ceid=US:en



| 日本語 | "hl=ja&gl=JP&ceid=JP:ja" |

| US英語 | "hl=en-US&gl=US&ceid=US:en" |

| イギリス英語 | "hl=en-GB&gl=GB&ceid=GB:en" |

Digital Nomaについての海外ブログ
[1](https://chrisguillebeau.com/feed/)




参考:https://qiita.com/KMD/items/872d8f4eed5d6ebf5df1

https://qiita.com/tachibanayu24/items/5877ce81c6a518fa7251


ってことは、他人のブログからRSSさえ取り出せれば、okってことか。
→うーん。RSSは[feedy](https://feedly.com/i/welcome)で機能するから、ディベロッパー用はAPIってことじゃない？
--------------------------------------------------------------------------------------------
予備知識：
スクレイピングの[gemファイル](https://github.com/sparklemotion/mechanize)(Mechanize)
そのファイルの[使い方](https://qiita.com/shizuma/items/d04facaa732f606f00ff)
スクレイピングについて困ったら見る[サイト](https://services.sms-datatech.co.jp/pig-data/)
スクレイピングで[こんな事](https://services.sms-datatech.co.jp/pig-data/usecase/)ができる
--------------------------------------------------------------------------------------------



# ちょっとまとめる

Digital Nomadについてのニュースまとめサイトを作りたいなら、APIをRailsで叩く。だから、[NewsAPI](https://newsapi.org/s/google-news-api)とかのサイトを使ってニュースを取得する。
叩き方は、[この動画](https://www.youtube.com/watch?v=0fFx9BrP_8g)


# これは、railsでAPIを作る(今回は該当しない)
https://qiita.com/c5meru/items/1c921676de8a5a038f70


補足

https://qiita.com/hamaup/items/cd7212aa1d0b1f0e37de


わかった事
APIは、JSON形式のデータ。(見た目はRailsハッシュに似ている。)
知りたい事

# railsでAPIを叩く(今回の目的はこれ)
## キーワード:

URL.encode_www_formメソッド: 別の形式データに変換すること。


今日はここまで。

## 感想:　
## APIについてわからなかったからググりまくったら1日が終ってしまった。googleにはうまくまとまってないサイトや、説明が曖昧なサイトがたくさんあることに気がついた。だから、時間を節約するためにも、**ググるならまずqiita**。これを徹底していきたいと思う。 　

明日もやる。
