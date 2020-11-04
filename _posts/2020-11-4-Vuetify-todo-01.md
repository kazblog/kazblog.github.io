---
layout: post
title: "Vuetify導入に丸一日かかった。そのプロセス。"
date: 2020-11-4 12:39:36 +0900
categories: Vue
permalink: /vuetyfy-dawnroad
excerpt_separator: <!--more-->
---

<!--more-->

## うまくいった方法


https://github.com/davidcsejtei/vue-with-vuetify
これをcloneして、readme通りにやったら行けた。vuetifyのパーツをコピペしたら、行けた。

## Vuetyfyのインストールプロセス。

前提: vue run serveまで完了している。

```
 $ cd プロジェクト名 
 $ vue add vuetify
```

$ vue add vuetifyを実行したら、エラーが出た。

```
Error: You cannot call "get" on a collection with no paths. Instead, check the "length" property first to verify at least 1 path exists.
```

https://github.com/vuetifyjs/vue-cli-plugins/issues/140

>i could solve my problem, there must be the following code in the main.js, otherwise the error will occur. So just add this code before installation:<br>
> new Vue({<br>
    render: h => h(App),<br>
}).$mount('#app');

これで、このエラーが解決した後に、また別のエラー。<be>

```
 Error: The package.json file at '/Users/hoge/Desktop/vuetifyPractice/package.json' does not exist
```
↑これは、ただ正しい作業ディレクトリにいなかっただけだった。
<br>
https://github.com/vuetifyjs/vue-cli-plugins/issues/140

のスレッドの最後に、
>I think the main issue has the same problem not using vue 2!

vue3を使っていたが、vue2でvuetifyをダウンロードしてみる。

<br>
この前よりか進んだ。

```
✔  Successfully installed plugin: vue-cli-plugin-vuetify

? Choose a preset: Default (recommended)

🚀  Invoking generator for vue-cli-plugin-vuetify...
📦  Installing additional dependencies...

added 7 packages from 5 contributors in 11.313s

66 packages are looking for funding
  run `npm fund` for details

⚓  Running completion hooks...

✔  Successfully invoked generator for plugin: vue-cli-plugin-vuetify
 vuetify  Discord community: https://community.vuetifyjs.com
 vuetify  Github: https://github.com/vuetifyjs/vuetify
 vuetify  Support Vuetify: https://github.com/sponsors/johnleider


```
しかし、vuetifyのファイルがまだ全てダウンロードされていない。。。


<br><br><br>

次のやり方。
<br>

```
$vue create
```
と同じ意味で、


```
$vue ui
```

でもワークする。vuetifyは、コマンドではなく、ブラウザで操作してダウンロードすることができる。

<br><br>
余談
<br>
Typescriptっていう言葉がvue関連のことをググると、なんども出てくるから、それについて調べた。<br>

## typescriptとは。

一言で言うと、「型定義できるJavaScript」

位置付け:<br>
AltJS (Alternative JavaScript) > TypescriptやcoffeeScript、Opal<br>
AltJS とは、JavaScript の代わりとなる 言語の総称です。
その言語で書いたものを JavaScript に変換して使用します。<br>


・型定義が使える。変数に異常があったら、エラーで気づかせてくれるらしい。以前は、本番に乗せるまで、コンピュータは気づく機能がなかったらしい。(戻り値と引数も。)<br>
・その他クラスが使えたり、外部ライブラリも使える。<br>
うーん。今までバックエンドでできていた機能が、ブラウザでも使えるようになったということかな？<br>

------
<br>
仮説: <br>
typescriptをインストールしていないと、vuetify動かないのかな？

<br><br>

https://github.com/davidcsejtei/vue-with-vuetify
これをcloneして、readme通りにやったら行けた。vuetifyのパーツをコピペしたら、行けた。
