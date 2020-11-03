---
layout: post
title: "VueCliでtodoリストを作る01"
date: 2020-11-3 12:39:36 +0900
categories: Vue
permalink: /vueCli-todo01
excerpt_separator: <!--more-->
---

<!--more-->

## VueCliを使う前の準備
nodeのインストール
```
$ npm install -g @vue/cli
```

##VueCliの始め方
```
$ vue create アプリ名
```
```
$ cd アプリ
```
```
$ npm run serve 
```
or 
```
$ vue ui
```
then show up these one on your browser!<br> 
Welcome to Your Vue.js App

## いくつかのルール
src>components>HelloWorld.vue内の話。
```vue
<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>
```
template内には、divは一つだけ。もう一つdivを作るとエラーになる。

## テンプレートsrc>components>something.vue

```vue
<template>
    
</template>

<script>
export default {
    
}
</script>


<style scoped>

</style>
```

## エラー
```
Failed to compile.

./src/components/TodoItem.vue
Module Error (from ./node_modules/eslint-loader/index.js):

/Users/kazumawada/Desktop/Vue-crashCourse/vue-crash/src/components/TodoItem.vue
  20:9  error  Unexpected mutation of "todo" prop  vue/no-mutating-props

✖ 1 problem (1 error, 0 warnings)
```

```
vue/no-mutating-props
```
これをググったら、たくさん出てきた。thisの書き方が問題らしい。(今の所)

```
methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  }
```
