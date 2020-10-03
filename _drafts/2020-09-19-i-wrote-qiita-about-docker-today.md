---
layout: post
title:  "dockerハンズオンで学習"
date:   2020-09-19 12:39:36 +0900
categories: Rails_study_log
permalink: :categories/:year/:month/:day/:title/
author: "kaz"
excerpt_separator: <!--more-->
---
<!--more-->


今日の成果。qiita1記事書いた

https://qiita.com/kazumawada/items/e0320aa8e05badc52023

# 以下が解決までのlog

同じエラーが出ている人への解決策があった。
'maybe try running it as sudo docker ... instead of docker .... The user that you are running as may not have permissions to talk to /var/run/docker.sock on that system.'
[そもそもsudoってなんだ？](https://wa3.i-3-i.info/word11269.html)
他のユーザー権でコマンドを打つ事。また、一時的にroot権限を使う方法。

> The Docker daemon always runs as the root user.
https://docs.docker.com/engine/install/linux-postinstall/


deamnは、root userで起動するのか。
では、コマンドのroot userとは。
管理者
普段は、root userを使うと、全ての権限があり、なんでもできてしまうので、危険。常にroot以外のユーザーで操作するのが望ましいらしい。
root user=スーパーユーザー
$の代わりに＃で表示されるらしい。
ってことは、＃の状態ではないと、Dockerのdeamonは起動しないの？[このチュートリアル](https://www.youtube.com/watch?v=fqMOX6JJhGo&feature=youtu.be)ではそんなことなかったけどな。



----------

Docker学習（ハンズオン）
https://kodekloud.com/p/docker-labs


Docker続き
34:34

https://www.youtube.com/watch?v=fqMOX6JJhGo&&feature=youtu.be


[https://youtu.be/fqMOX6JJhGo](https://youtu.be/fqMOX6JJhGo)

