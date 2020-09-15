---
layout: post
title:  "簡単な記事を探すと、余計遠回りになると知った日"
date:   2020-09-15 12:39:36 +0900
categories: Rails_study_log
permalink: :categories/:year/:month/:day/:title/
author: "kaz"
excerpt_separator: <!--more-->
---



難しいからほかの記事、ブログを参考にしようは、オススメしない。それは簡単にできることを探していて、余計遠回りになるから、この「ちょっとむずかしいな早く終わらせたいな」という考えは、エンジニアにとって危険な考え。難しくても一歩ずつ進もう。難しくても、qiitaの一文字目を目に入れることからスタートしようと思った。
https://qiita.com/hirokidaichi/items/27c757d92b6915e8ecf7
<!--more-->
<br>

# 9/15以下はただのlog
今日、cloud9の容量がいっぱいになったから、新しい環境を作って、githubからcloneして、再開しようとしたんだけど、こんなエラーが出た。

Could not find proper version of railties (6.0.3) in any of the sources

これで解決せず

https://stackoverflow.com/questions/37117230/rails-new-gives-could-not-find-proper-version-of-railties-4-2-5-1-in-any-of-t


今度はこれ。

https://qiita.com/___xxx_/items/42917092ca1c3aabda15


うまくいきそうな直前で、(bundle installの直前で、)このエラー。
there was an error while trying to write to `/tmp/bundler-compact-index-20200915-28859-tbiyab/versions`. There was insufficient space remaining on the device.
cloud9の容量が大きくなりすぎたらしい。

,,,,,ううーん。めんどくさい。cloud9は、初心者向けの開発環境ツールだし、それに詳しくなっても意味ない。そこがやる気が出ないもとだ。

よし、これを機に開発環境を自分で作ってみよう。
Dockerで。

さっそくググる。良さそうなのピックアップ

https://y-ohgi.com/introduction-docker/
https://labs.play-with-docker.com/


https://qiita.com/etaroid/items/b1024c7d200a75b992fc

https://qiita.com/etaroid/items/88ec3a0e2d80d7cdf87a

https://qiita.com/etaroid/items/40106f13d47bfcbc2572

https://qiita.com/gold-kou/items/44860fbda1a34a001fc1

https://qiita.com/kawasin73/items/2253523be18e5afd994f

https://qiita.com/Moo_Moo_Farm/items/0d08da27371272ed1390


昨日の反省として、APIについてググりまくっていたが、手を動かせる教材を避けていた。めんどくさいから。手を動かすことが一番理解のスピードを上げることなのに。だから今回は、Dockerとはとか調べずに、とりあえずこの[入門docker](https://y-ohgi.com/introduction-docker/)で手を動かして見る。



# ちょっと疑問

Circle CIって？
ビルド、テストとかができるらしい。herokuと似てるのかな？共同開発用のherokuかな？まあいいや。まだ遠い先の話だ。




# Dockerを手を動かして理解する。
## 流行った理由:

コンテナという概念は前からあったが、Dockerは、[配布の容易性]が人気を後押しした。
この仕組みを用いることで、ローカルから本番まで同じ環境で作業することができる。


## Why Docker?

どの環境でも動く

今あなたが書いている環境を、そのままスナップショットして、チーム内で共有できる。ステージングできる。本番に送ることができる。

確実に動作するスナップショット

オーバーヘッド:https://wa3.i-3-i.info/word12471.html
計算機にかかる負担。従来は、物理レイヤーの仮想化。Dockerは、切り離された場所から環境を実現。確かにな。vagrantが10GBくらいあったような。。


## Immutable Infrastructure(変わらない基盤):

これは説明を読んでも、実際にDocker以外で開発を行ったことがないから、意味がよくわからなかったが、DockerfileとDocker imageがImmutable Infrastructureを実現していることはわかった。


## VMとDocker

VIMはあなたのコンピュータを仮想化。
MacOSにWindowsを入れたり。当然だが、あなたのパソコンにフィジカルに負担がかかる。

Dockerは、プロセスの仮想化。

早速試す(https://labs.play-with-docker.com/)

出て来てわからなかったキーワード
nginx(エンジンエックス: https://wa3.i-3-i.info/word12859.html):webサーバのソフトのひとつ。リバースプロシキ(https://wa3.i-3-i.info/word1755.html, なんかやったな.サーバーとクライアントの間に仲介として入ることで、負荷分散できたり、身元を隠せたりすることができる。)ができる

クライアントとサーバーは同じで。どちらも両方の機能を持つ。で、サーバーをサーバーと呼べるのは、webサーバーのソフトがあるから。
つまり、箱(ハード)+nginx＝サーバーの出来上がり。


----------
## Docker imageとは？

環境のスナップショット。

Ubuntuを動かす。
nginxのようなソフトウェアを動かせるし、ubuntuのようなOSも動かせる。
Docker Imageは、公式のDocker hubにOS、ソフトウェアを公開している。

Bashを使用する。
Bash is a Unix shell(in between the computer and the person) and command language
shell = Bash
bashとカーネルの違いは？カーネルが奥深く、、その外側をbashがいる。人間は、直接カーネルとやりとりせず,bashを経由して会話する。

bashに入ったら、$→#になった。


## Tag

DockerImageには、tag機能がある。バージョンを指定しやすくする。


# ここまでのまとめ
- image（スナップショット）は、DockerHubから取ってくることができる。
- tagで特定のバージョンを指定することができる。<イメージ名>:<タグ>

例

    $ docker run python:2.7 python --version



## DockerFile
![https://y-ohgi.com/introduction-docker/2_component/dockerfile/](https://paper-attachments.dropbox.com/s_7FF33929F9ABBA958EF55D6488861AC28199DA147166B320C5E7347A1052E446_1600134675075_FireShot+Capture+050+-+dockerfile+-++Docker+-+y-ohgi.com.png)


DockerImageを自分で作成する。

DockerImageをローカルで開発する。
↓
DockerImageの命名
↓
DockerHubへアップロード
↓
ローカルのコンテナ、Imageを削除。同名のImageがあったら、ローカルを参照してしまうのを防ぐため。
↓
DockerHubからImageをpullする。
↓
Imageを実行。



> Dockerfileを記述してDocker Image を作成する。
> Docker Image はDockerレジストリへアップロードすることで容易に保管/配布ができる。
> Dockerfileは基本的に7個のコマンドの組み合わせで作成できる。



## DockerContainer
![](https://paper-attachments.dropbox.com/s_7FF33929F9ABBA958EF55D6488861AC28199DA147166B320C5E7347A1052E446_1600134675075_FireShot+Capture+050+-+dockerfile+-++Docker+-+y-ohgi.com.png)


**スナップショットから起動したプロセス。**


![](https://paper-attachments.dropbox.com/s_7FF33929F9ABBA958EF55D6488861AC28199DA147166B320C5E7347A1052E446_1600149930210_image.png)


DockerContainerは**5つ**の状態がある。


## Image: ImageからContainerへ起動。
## Runnning: 　Containerが起動。
## Stopped: 起動したものが終了した場合。
## Paused: pause明示的にコマンそを打つと、実行される。
## Deleted: rmで明示的にコマンドを打つと、実行される。



## プロセスの隔離

ホストOSや他のコンテナとは隔離された場所で実行されているという認識。



----------
# Network

Dockerでは、1コンテナで1プロセス動かすという決まりがある。
複数のプロセスを強調させたい場合に、ネットワークを使う。↓


![](https://paper-attachments.dropbox.com/s_7FF33929F9ABBA958EF55D6488861AC28199DA147166B320C5E7347A1052E446_1600150937015_image.png)


このように複数プロセスを強調させて動かすには、(Dockerのコンテナを繋げて作業するってことかな？一プロセス一コンテナだから、nginxで1コンテナってことだもんね。)ネットワークを使う必要がある。

networkまたは、NetworkDriver。2種類ある。

１
https://y-ohgi.com/introduction-docker/2_component/network/#1-bridge
2
https://y-ohgi.com/introduction-docker/2_component/network/#2-host


![](https://paper-attachments.dropbox.com/s_7FF33929F9ABBA958EF55D6488861AC28199DA147166B320C5E7347A1052E446_1600151284186_image.png)



- 1プロセス1コンテナ、復数プロセスはネットワークを通して通信を行う。

すでにコンテナないに、プロセスがある場合、

    docker run --network=myapp -it amazonlinux:2 curl nginx2:80

これでそのコンテナ内に追加したら、エラーになる。（1プロセス1コンテナ。）


- Bridgeを基本的に使用する。




----------


# Volume

データを永続化させるための機能。

![](https://paper-attachments.dropbox.com/s_7FF33929F9ABBA958EF55D6488861AC28199DA147166B320C5E7347A1052E446_1600152028880_image.png)


DockerContainerは基本的に一時的なもので、コンテナ上で作成されたファイルはコンテナのライフサイクルの終了と共に消えてしまいます。Volumeはデータ保持・永続化のために設計されており、コンテナのライフサイクルとは独立してファイルの管理を行います。


ライフサイクル(一時的)→Volume(永続的)



----------
# 設計

じゃあ、開発環境実際にどうやってつくんの？

まずはじめに、コンテナ設計の12の方法論
[The Twelve-Factor App （日本語訳）](https://12factor.net/ja/)



## セキュリティ

Dockerもプログラミング言語同様、セキュアな状態を保つことが大事。


- rootユーザを使わない（アクセスされたらまずい）
- 他人のimageを信用しない。(hubのimageリストにもウイルスはある。)公式のものを利用しよう。
- ビルド時に秘密情報を与えない。(それもスナップショット取られるから。)
- .dockerignoreファイルを使う。

、、、じゃあこれを機に、gitignoreってなんだっけ？
pushしたくないファイルをそこに置いておく。

続き
https://y-ohgi.com/introduction-docker/3_production/image/

,,,直感だけど、本で体系的に学ばなきゃわからないやつだと思うDockerは。グーグルだけだと力つきる。
https://www.amazon.co.jp/dp/4297100339/ref=as_sl_pc_tf_til?tag=yohgi-22&linkCode=w00&linkId=a5336422aa127e3f56799776b70e652e&creativeASIN=4297100339




(補足: コマンドライン 「vi」は、ファイルの中身をコマンド内で編集することができる。)
