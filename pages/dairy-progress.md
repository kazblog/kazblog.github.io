---
layout: page
title: 今日の積み上げ
permalink: /dayry-progress/
---


<h3> 

<a href="https://www.notion.so/1429884b6b694185b30a1b56cf5abc0c" target="_blank" class="ml-3">
  <i class="fas fa-circle"></i> 今日の積み上げ
</a>

</h3>






<!-- <h3>2020/11~ 毎日学習した事を記録しています。</h3>

<br><br>


<h3>2020-11</h3><br><br>

・ポートフォリオの設計図を書いた。<br>

・rails6にvue, vuetifyを導入した。<br>

・gitのissueを作り、commitを紐づけて管理<br>
・ vueをインストールして、railsからjsonを受け取り、ブラウザに表示させる事<br>
・RailsApiの作成方法を学んだ。<br>



<h3>2020-12</h3><br>
・RailsAPIの作成を進めた。user,post,followerなどのmodel, controller作成<br>
・vueにanxiosを導入して、APIを出力しようとしたがエラー。未解決。<br>
・oDocker環境のVueにVuetifyを追加したらエラー。未解決。<br>
12/14<br>profileと投稿画面のstaticPageをVuetifyで作成した。<br><br>
12/8<br>apiとvueでどうやって投稿機能を作るのかググった。<br><br>
12/15<br>railsのform_withが、コントローラー、DBと、どう機能しているのか学習した。rails apiを使ってvueにformを作るのは、コードの量が多くなって難しい。rails apiをやめて、railsファイル内のjavascriptにvueを導入し直すか悩む。明日のググり次第で決める。<br><br>
12/16<br>railsのform_withについての理解を深めた。「送信を押すと、railsがcreateアクションかupdateアクションのどちらかに行くか＠インスタンスの情報を見て判断する」ということがわかった。今までのなんとなくから具体的に理解できたのが良かった。<br><br>
12/17<br>rails内にvueを入れる作業で、webpackerやyarnのエラーにつまった。<br><br>
12/18<br>railsAPI、フロントの開発スタイルを変えて、rails内にvueを入れることにした。その移行作業をした。<br><br>
12/19<br>webpacker/yarnエラーが解決できず、前に進めないので、新しく環境を構築することにした。その作業を行った。<br>
12/20<br>RailsとVueがどうviweで連携しているのかを学んだ。(まだエラーでブラウザにviewは表示されていないが。)<br>
12/21<br>railsとvueで、どのようにviewが作られるのか学んだ。webpacker,yarn等のエラーも解決できた。頭がスッキリしている状態だと、生産性が何十倍にもなると誰かが言っていたけど、それを実感できた日だった。<br><br>
12/22<br>erbにvueのコンポーネントを入力する時、erbで使うオブジェクト名と同じ名前(headerとか)を使うとエラーになるから、vueで事前に名前を変えておくことを知った。vueでrouterを定義したら、忘れずにrailsのrouterにも記入しておく。[このqiita](https://qiita.com/naoki85/items/51a8b0f2cbf949d08b11)がとても参考になった。明日は、vuetifyが表示されなかったエラーを解決して行く。自分が今何をやっているのかわからなくなったら、一旦コンピュータを閉じて、紙にログや、今やってること、実現したいことを明確にした方がいいと思った。<br><br>
12/23<br>Vuetifyをダウンロードしたがうまく表示されず。明日もググる。<br><br>
12/24<br>Vuetifyを正しくダウンロードできた。<br><br>
12/25<br>routerをインストールしたが、うまく機能しなかった。わからないときは、落ち着いて紙に書き出すことが大事だと思った。<br><br>
12/26<br>Userモデル、コントローラー、signUp機能を作成した。rails、vueでviewの使い分けをする必要があると気付いた。<br><br>
12/27<br>Userの削除、更新、編集機能を追加し、logout, loginを作成した。<br>
12/28<br>Restfulのdeleteがうまくいかなかったところを今日解決できた。最初に一気に集中する事が大事。だらだらと始めると、立て直すのに労力を使う。最初にガッと。<br><br>
12/29<br>mailerと投稿機能を作った。朝すぐ4hやって、運動して2hやるっていう自分のルーティーンができてきた。その後は、6h以上やっても集中できないから、明日のためにリラックスする時間にするべきだと思った。<br><br>
12/30<br>投稿のdelete機能とfollowing,followedの実装を半分くらいまでやった。<br><br>
12/31<br>followの実装を終えた。(少しエラーが残っている)次からrspec、返信機能、ニュースAPIなどを作って行く。画面のデザインはvue(webpack),vuetifyでやろうと思ったけど、erbにvueを馴染ませるのがややこしい。まだrailsが理解しきれていないのに、また複雑なものに手を出すと、抱えきれなくなって、過去のrailsAPIを断念した時と同じことになりそう。まずはrailsでしっかりと作品を作って、デザインは、cssのフレームワークを使うことにした。そのフレームワークに関する記事を書いた([シンプルで美しいCSSフレームワーク　samantic-ui　をRailsに導入する。](https://qiita.com/kazumawada/items/933acc82558800235280))<br>もう一つは、pathについても学んだ。わざわざさ今のファイル位置からassets/image/image.jpgまでのpathを書くのは流石にめんどくさいと思い調べたら、やはりrailsがimage_tagといのを用意していた。これにimage名を書けばよくて、pathをいちいち調べる必要がないから楽だ。[【Rails】画像のパスを指定する](https://qiita.com/d0ne1s/items/0af5e99feafd5172d8ce)<br><br>


<h3>2021-1</h3><br>

1/1<br>RSpecをインストールした。semanticUIでpage/homeをレイアウトした。<br><br>
1/2<br>semanticUIでhomeのlayuotを作成した。<br><br>
1/3<br>cssフレームワークをsemanticUIからBootstrapに移行することにした。semanticUIは、他者とのデザインの差別化のために選んだが、なんというかまだrailsのRSpec、拡張機能、デプロイで使うAWSがあるのに、また学習する必要があるCSSフレームワークがあると、精神的にきつい。ポートフォリオを作りきれなかったら、元も子もないから、元々知っていたBootstrapで実装することにした。差別化とか、すごい機能をつけるとか、そういう考えは、railsで作る拡張機能、railsのRSpec、デプロイなどができてから考えるべきだと思った。あれもこれもと手を出すと、精神的にきついし、手が止まる。まずは自分のできる範囲から手をつけて、徐々にステップアップしていくことが大切だと思った。いきなり沢山手を出すと死ぬ。一歩一歩進む。<br><br>
1/4<br>Bootstrapでpage/homeをレイアウトした。semanticUIとは違い、元々学習したことがあったので、早く実装することができたし、img-fluidはぼやけないし、レスポンシブしっかりするし、本当に楽だった。フロントをvueからsemanticUIそしてBootstrapと、どんどん当初の計画とは違ってきたけど、前回も書いたように、railsの拡張機能、RSpecの導入、デプロイなど、まだ優先してやることがあるので、デザインでつまづいてもしょうがないから、楽に実装できるBootstrapにして良かった。明日もやる。<br><br>
<hr>
1/5<br>Bootstrapでtabによる画面切り替えとプロフィールのデザインをやった。signUpにformの項目を追加するときに、railsチュートリアル通りにやると考えなくてもできてしまうが、今回は、どうやってcontrollerとformがデータのやり取りをしているのか理解できた。自分で新たな機能を実装しようとすると、自分の頭で考えるから、よく理解できるし、記憶に残る。<br><br>
<hr>
1/6<br>signupに項目を追加した。form_withとコントローラーの繋がりが良く理解できた。form_with
のmodel@userがuser#newと繋がっていて、formの内容、nameやemailなどがcontrollerにあるuser_paramsで定義されていて、DBとも繋がっている。データが送信されたら、その@userの情報が全く新しければrailsがuser#createへ送り、すでに作られたデータなら、user#updateへ自動で送ってくれる。<br><br>
<hr>
1/7<br>投稿のタイトル、tag、ユーザーのアイコンを設定した。signupを一から実装したため、formに慣れていたから、signupと同じ要領で投稿内容のデータのやり取りを設定できた。<br><br>
<hr>
1/8<br>簡単ログインを実装した。qiitaとうの良記事では、deviseの導入が前提になっていたが、自分は導入していなかったため、新しくゲストユーザー用のcontrollerを作り、createアクションの中にDBにあるゲストユーザーのemailを書いた。そのformリンクを「簡単ログインボタン」にした。RSpecを初めて学習した。minitestよりも直感的で見やすいことがわかった。<br><br>
<hr>
1/9<br>自分のアウトプットブログ(このブログ)のデザインを見やすく改良した。明日実装予定の「投稿記事詳細」と「記事一覧」をどのように実装するか紙に書いた。コードをvscodeでいきなり書くより、紙に書いた方が実装するスピードが早い。<br><br>
<hr>
1/10<br>記事一覧をのデータを他のモデルからextendしてくる方法を学んだ。「rails concern」, 「extend ActiveSupport::Concern」とかでググると出てくる。<br><br>
<hr>
1/11<br>RSpecについて。下のようなテストコードがあったとする。本当に正しいテストを書いているのか確認するための方法は2つある。

```ruby
  it "is valid with a name, email, password, year and bio" do
  user = User.new(
    name:  "main-user",
    email: "main@example.com",
    password: "thisispassword",
    year: "1年",
    bio: "hello!"
  )
  expect(user).to be_valid
end
```

一つは、toをto_notに変えてみる<br>
もう一つは、user.rbのvalidationをコメントアウトしてみる。↓

```ruby
 #validates :name,  presence: true, length: { maximum: 100 }
```

<br>
<br>
<hr>
1/12<br>RSpecで、Userモデルのvalidationと正しいページが表示されるかどうかのテストを行った。RSpecを書き始めて2日目だけど、早くもminitesuより見やすいし、書きやすいことを実感している。<br><br>
<hr>
1/13<br>RSpecで、gem: shoulda-matchersをインストールしてテストを書いた。validationが一行で書けるから、楽だった。今まで

```
# it "is invalid without a name" do
  #   user = User.new(name:nil)
  #   user.valid?
  #   expect(user.errors[:name]).to include("can't be blank")
  # end
```

gem　追加後

```
  it { is_expected.to validate_presence_of :name }
```

楽だ。<br>
返信機能を実装した。model同士の紐付け、一部のcontrollerの定義はできたが、outputをどう定義してviewに書けばいいのかわからなかった。それによって、自分は、返信のデータがどこにあるのか理解しきれてないということがわかった。ここまでプログラミングしてきて、つくづく「結局はデータのやりとりなんだな」と思った。

<br><br>
<hr>
1/14  <h4>いいねの実装・DBアソシエーション・レファクタリング</h4> <br>「いいね」を実装して見た。実装している最中に、データのやりとりがどうなっているのかわからなった。→アソシエーションを学習した→「いいね」再挑戦→<br>
新しいif分岐の書き方を覚えた。headerがhomeレイアウトの中にあった時、取り出して、一番上に持ってくるとデザインが崩れてしまう。homeだけ特定の位置で、あとは通常の場所に指定したい時に必要になった。

```ruby
　#controller_nameでもいける。
  <% unless action_name == "home" %>
  <%= render 'layouts/header' %>
  <% end %>
```
意味は、#home出なければ、renderを表示する。

<br>
<hr>
1/15<br>今日やった事→返信機能を実装した。 <br>
理解した事→ネストしたルーティングの場合のfoemの書き方は、model[comments, posts]と書く。render,partial,localsの意味。newとbuildはやっていることがほとんど同じ。<br><br>
<hr>
1/16<br>いいねを実装した。けどエラーで詰まった。まだ、has_manyで格納されたDBをどうやってコントローラで定義すればいいのかわからない、qiitaなどを見ても理解ができないから、DBのアソシエーションが理解できていないんだと思う。明日もやってみる。「多対多 rails」とかでググると良さそう。<br><br>
<hr>
1/17<br>やった事→いいねを実装した。まだcreateのところで、どうやってデータを取ってきているのか理解ができない。

<br>学んだ事→

```ruby
rails g model Like post:references user:references

↓
これで、belongs_toが自動で入る
↓
class Like < ApplicationRecord
  belongs_to :post
  belongs_to :user
end

migrateするとこうなる

↓

create_table "likes", charset: "utf8mb4", collation: "utf8mb4_0900_ai_ci", force: :cascade do |t|
    t.bigint "post_id", null: false
    t.bigint "user_id", null: false
    t.datetime "created_at", precision: 6, null: false
    t.datetime "updated_at", precision: 6, null: false
    t.index ["post_id"], name: "index_likes_on_post_id"
    t.index ["user_id"], name: "index_likes_on_user_id"
 end

add_foreign_key "likes", "posts"
add_foreign_key "likes", "users"
```

<br>


countが1だったら、Like。それ以外だったら、Likes
```ruby
<%= @post.likes.count %> <%= (@post.likes.count) == 1 ? 'Like' : 'Likes'%>
```

<br>
<hr>
 -->




