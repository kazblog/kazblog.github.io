---
layout: post
title:  "think-cleary"
date:   2020-09-21 12:39:36 +0900
categories: Rails_study_log
permalink: :categories/:year/:month/:day/:title/
author: "kaz"
excerpt_separator: <!--more-->
---

<!--more-->

## 感想
ただやるのではなく、目的に沿ってやる。自分のサービスは、rails tutorialに沿って進めていたが、途中でやる気がなくなってきた。なぜか考えてみたら、それが必要か不要か明確にせずにただコードを書いていたから。そこで、今はユーザー登録機能ではなく、APIが必要だとわかった時に、APIをググるやる気は、ただコードを書いていた時よりも「理解したいと言う思いが強くなっていた」だから、ただやらないで、なんでやってるかわかってからやろうと思った。



未読記事

https://knowledge.sakura.ad.jp/15253/


参考資料
dockerやっぱ、遠回りが近道だよ。

https://www.youtube.com/watch?v=fqMOX6JJhGo&


[https://youtu.be/fqMOX6JJhGo](https://youtu.be/fqMOX6JJhGo)

https://www.youtube.com/watch?v=Fq1PH0Gwi8I&


[https://youtu.be/Fq1PH0Gwi8I](https://youtu.be/Fq1PH0Gwi8I)

https://kazumawada.github.io/rails_study_log/2020/09/15/face-it/
api

https://www.youtube.com/watch?v=aD6JvHKNPPM&&feature=youtu.be


[https://youtu.be/aD6JvHKNPPM](https://youtu.be/aD6JvHKNPPM)

https://www.youtube.com/watch?v=GZvSYJDk-us&&feature=youtu.be


[https://youtu.be/GZvSYJDk-us](https://youtu.be/GZvSYJDk-us)


https://qiita.com/vzvu3k6k/items/dd45ad293ae2d60c7a4e


https://www.google.com/search?rlz=1CDGOYI_enJP861JP861&hl=en-US&sxsrf=ALeKk00rdg6kvL_kDT5izbxYRzfq8wCGyg%3A1600406582382&ei=NkRkX9DQFprZ-QaXj5uwCQ&q=ruby+parse+%E3%81%A8%E3%81%AF&oq=ruby+parse+%E3%81%A8%E3%81%AF&gs_lcp=ChNtb2JpbGUtZ3dzLXdpei1zZXJwEAMyBQgAEM0COgQIABBHOgQIABBDOgIIADoECCMQJzoHCAAQFBCHAjoGCAAQBBAeOggIABAIEAQQHlD2qQVYpdsFYK_dBWgCcAJ4AIABzgKIAcUGkgEHMi4zLjAuMZgBAKABAcgBCMABAQ&sclient=mobile-gws-wiz-serp#

https://stackoverflow.com/questions/5410682/parsing-a-json-string-in-ruby

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

https://www.youtube.com/watch?v=GZvSYJDk-us&&&feature=youtu.be


[https://youtu.be/GZvSYJDk-us](https://youtu.be/GZvSYJDk-us)


達成すること
年内に外部APIを使ったサービスをrailsで作成する。Rails Tutorialをなぞって、その後に拡張機能を自分で実装する。そしてDocker, AWS, AJAXを使う。

そのために今日やること
RTとDN(80%)
API(10%)
Docker(10%)


----------

Rails Tutorial

データベースの中身が正しいかどうか検証する。すなわち、有効な情報を送信して、ユーザーが*作成された*ことを確認します。


    assert_difference 'User.count', 1 do
          post users_path
    ・
    ・
    ・
    end



    form_with(model: @user, local: true) #siguup
    
    form_with(url: login_path, scope: :session, local: true) #login



moduleは、application_controllerにincludeすれば、自由に他のcontrollerで使えるのか。だから、いきなりcontrollerにlog_in(user)と書けるのか。

9章


> 具体的には、まずユーザーのログイン**情報を長く記憶する**方法（例えばBitbucketやGitHubが使っている方法）について学びます。その後、［remember me］チェックボックスを使って、ユーザーの**任意で****ログイン情報を記憶する**方法について学びます（例えばTwitterやFacebookも使っていますね）。


**情報を長く記憶する**

- セッションの永続化の第一歩として*記憶トークン（remember token）*
- `**cookies**`メソッドによる永続的cookiesの作成

　　＋
安全性の高い*記憶ダイジェスト（remember digest）*によるトークン認証にこの記憶トークンを　活用します。

(
session: 安全にデータが長く保たれる
cookie: 安全にデータを長く保つには、自分で対策をする必要がある。
)
じゃあ、なんでcookie使うの？
sessionメソッドで作るcookieは安全！！(sessionでは一時的なものしか作れないと言うことか。)
cookieメソッドで作成した永続セッションは危ない!!(remember meをつするなら、sessionメソッドはステートレスだから使えない。cookieを自ら永続化する必要があると言うことか。)





1. 記憶トークン(`**SecureRandom**`モジュールにある`**urlsafe_base64**`メソッド)
2. ブラウザのcookiesにトークンを保存するときには、有効期限を設定する。
3. トークンはハッシュに変換してからデータベースに保存する。(トークン→ハッシュ→DB)
4. ブラウザのcookiesに保存するユーザーIDは暗号化しておく。
5. 永続ユーザーIDを含むcookiesを受け取ったら、そのIDでデータベースを検索し、記憶トークンのcookiesがデータベース内のハッシュ値と一致することを確認する。(`**authenticate**`メソッド)

↑(has_secure_passwordと似ている)


10章
ユーザーの削除、一覧表示、更新

ニュースサイトのユーザーってどんな機能が使えることを許されているんだろう。
てかユーザーいらなくね？

わからないことがわからないから、とりあえずユーザーいらないんだったらいらないでいいじゃん。

じゃあ、必要なのは？API！！！


----------

j










# API
----------
https://www.youtube.com/watch?v=GZvSYJDk-us&


[https://youtu.be/GZvSYJDk-us](https://youtu.be/GZvSYJDk-us)

・APIはそれが何をするのかを知っていれば、中身を知る必要はない。

・API自体は、すごく範囲が広い。rubyに組み込まれている関数、例えばlink_to
もAPI。それの中身は知らなくても、それを書けばリンクを表示してくれる。

・プログラムが、魔法、ブラックボックスと呼ばれるのは、APIのおかげ。

・だから私たちが考えるのは、それをどう自分のプロgプログラムに組み込むかと言うことだけ。


- ステートレス：　一回で完結する通信。記憶されない。(HTTPの説明で出てきた。)
- RESTは、HTTPでリクエストを送ると帰ってくる(URLを送る)、ステートレス、
- OAuth Token: アクセスとーくん。これでDBにアクセスできる。




https://apilist.fun/


ザAPIの企業

https://www.twilio.com/


ググるキーワード
外部API
external API 


----------

こうだと思った。
適当にコントローラーに貼って、
 def news
        url = URI("https://news67.p.rapidapi.com/top/about-country")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["x-rapidapi-host"] = 'news67.p.rapidapi.com'
request["x-rapidapi-key"] = 'api-page-endpoints_form-param_mashape-key_default'

response = http.request(request)
@output = puts response.source
    end
    
    viewで
      <%= @output %>
      
      良さげ記事
      
      https://stackoverflow.com/questions/39994807/how-to-use-external-api-in-ruby-in-rails
      https://stackoverflow.com/questions/62916858/how-would-i-parse-json-in-ruby-to-give-me-specific-output
      どこでも共通してみる書き方
    uri = URI(url)

    response = Net::HTTP.get(uri)
    JSON.parse(response)

      

----------

    























