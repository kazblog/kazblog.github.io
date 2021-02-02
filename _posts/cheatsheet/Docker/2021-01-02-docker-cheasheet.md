---
layout: post
title:  "Dockerのチートシート"
date:   2021-01-02 12:39:36 +0900
categories: cheatsheet
permalink: /docker-cheatsheet
excerpt_separator: <!--more-->
---
![image here](/assets/img/thumbnail/ten.jpeg)
<!-- <div style="text-align: center;">
<img src="/assets/img/thumbnail/ten.jpeg" width="550px" height="400px">
</div> -->
<!--more-->

わかりやすそう。aws,circleci puma nginxとかやるときに見て見る。
https://yumanoblog.com/docker/
 

<br><br>

## コンテナ、イメージの削除コマンド


```bash:bash
$ docker stop $(docker ps -q)
$ docker rm $(docker ps -aq)
$ docker rmi $(docker images -q)
```



## bundle installの後に実行

```bash:bash
docker-compose build --no-cache
```


## デバック

```
docker attach myapp_web_1
```


gistテスト
<script src="https://gist.github.com/kazumawada/1958832dbd311df8e7494180afbaf2be.js"></script>

https://gist.github.com/kazumawada/1958832dbd311df8e7494180afbaf2be





