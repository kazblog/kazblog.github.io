---
layout: post
title: "Vuetify入門"
date: 2020-11-4 12:39:36 +0900
categories: Vue
permalink: /vuetyfy-cheet-sheat
excerpt_separator: <!--more-->
---

vuetifyのgrid,menu,padding,margin,typography
<!--more-->

## vuetifyチートシート

参考: https://github.com/kazumawada/vuetify-basic-components

必ずv-app内に要素を書く。
<br><br><br><br>


```
<template>
  <v-app id="app">
    <router-view />
  </v-app>
</template>
```

・CDNでもvuetifyを導入できる。<br>
・Bootstrapみたいに、v-contentの中でflexが効いてくる。

```
 <body>
        <div id="app">
            <v-app>
                <v-content>
                    <playground></playground>
                </v-content>
            </v-app>
        </div>
        <script src="https://cdn.jsdelivr.net/npm/vue@2.x/dist/vue.js"></script>
        <script src="https://cdn.jsdelivr.net/npm/vuetify@2.x/dist/vuetify.js"></script>
        <script src="index.pack.js"></script>
    </body>
```

<br><br>

# Grid

bootstrapとよく似ていて、pとmで表す。1~12まで幅を設定できる。

```
<template>
  <div>
    <h3>Grid</h3>
    <v-card class="mt-5 mb-8">
      <v-card-text>
        <v-container>
          <v-row>
            <v-col cols="12">
              <v-card
                class="pa-2"
                outlined
                tile
              >
                Column
              </v-card>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="4">
              <v-card
                class="pa-2"
                outlined
                tile
              >
                Column
              </v-card>
            </v-col>
            <v-col cols="4">
              <v-card
                class="pa-2"
                outlined
                tile
              >
                Column
              </v-card>
            </v-col>
            <v-col cols="4">
              <v-card
                class="pa-2"
                outlined
                tile
              >
                Column
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-card-text>
    </v-card>
  </div>
</template>

```

<br><br>
[![Image from Gyazo](https://i.gyazo.com/864d5a59f74b010cfa6cad92e0fc6ada.png)](https://gyazo.com/864d5a59f74b010cfa6cad92e0fc6ada)




# メニュー


```
<template>
  <div>
    <h3>Menus</h3>
    <v-card class="mt-5 mb-8">
      <v-card-text>
        <v-app-bar
          color="deep-purple accent-4"
          dense
          dark
        >
          <v-app-bar-nav-icon></v-app-bar-nav-icon>

          <v-toolbar-title>App Title</v-toolbar-title>

          <v-spacer></v-spacer>

          <v-btn icon>
            <v-icon>mdi-heart</v-icon>
          </v-btn>

          <v-btn icon>
            <v-icon>mdi-magnify</v-icon>
          </v-btn>

          <v-menu
            left
            bottom
          >
            <template v-slot:activator="{ on }">
              <v-btn icon v-on="on">
                <v-icon>mdi-dots-vertical</v-icon>
              </v-btn>
            </template>

            <v-list>
              <v-list-item
                v-for="n in 5"
                :key="n"
                @click="() => {}"
              >
                <v-list-item-title>Option {{ n }}</v-list-item-title>
              </v-list-item>
            </v-list>
          </v-menu>
        </v-app-bar>
      </v-card-text>
    </v-card>
  </div>
</template>
```

<br><br>
[![Image from Gyazo](https://i.gyazo.com/f2500b9d2fc5cb3eee79b7fc8aa9e673.png)](https://gyazo.com/f2500b9d2fc5cb3eee79b7fc8aa9e673)



# paddingとMargin

```
<template>
  <div>
    <h3>Spacing=margin, Paddingのこと</h3>
    //mとpで表す。1~12まで
    <v-row>
      <h3 class="mx-auto">中央寄せ</h3>
    </v-row>
    <v-card class="mt-5 mb-8">
      //これで練習できる
      <v-card-text>
        <v-container
          class="spacing-playground py-0 px-2"
          fluid
        >
          <v-row>
            <v-col
              cols="12"
              sm="6"
              class="d-flex align-center"
            >
              <v-select
                v-model="paddingDirection"
                :items="directions"
                label="Padding"
                class="pr-2"
              >
                <template v-slot:prepend>
                  <strong class="primary--text">p</strong>
                </template>
                <template v-slot:append-outer>
                  <div> - </div>
                </template>
              </v-select>
              <v-select
                v-model="paddingSize"
                :items="paddingSizes.slice(1)"
                label="Size"
              ></v-select>
            </v-col>
            <v-col
              cols="12"
              sm="6"
              class="d-flex"
            >
              <v-select
                v-model="marginDirection"
                :items="directions"
                label="Margin"
                class="pr-2"
              >
                <template v-slot:prepend>
                  <strong class="primary--text">m</strong>
                </template>
                <template v-slot:append-outer>
                  <div> - </div>
                </template>
              </v-select>
              <v-select
                v-model="marginSize"
                :items="marginSizes"
                label="Size"
              ></v-select>
            </v-col>
            <v-col
              cols="12"
              class="orange lighten-3 pa-0"
            >
              <v-card
                :class="[computedMargin]"
                class="elevation-4"
              >
                <div
                  :class="[computedPadding]"
                  class="light-green lighten-3"
                >
                  <div
                    class="white text-center"
                    v-text="playgroundText"
                  ></div>
                </div>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
// CREDIT: Example taken from Vuetify Documentation
// https://vuetifyjs.com/en/styles/spacing#playground
export default {
  data() {
    return {
      directions: ['t', 'b', 'l', 'r', 's', 'e', 'x', 'y', 'a'],
      paddingSizes: ['auto', '0', '1', '2', '3', '4', '5', '6', '7', '8', '9', '10', '11', '12'],
      marginSizes: [
        'auto',
        '0', '1', '2', '3', '4', '5', '6', '7', '8', '9', '10', '11', '12',
        'n1', 'n2', 'n3', 'n4', 'n5', 'n6', 'n7', 'n8', 'n9', 'n10', 'n11', 'n12'
      ],
      paddingDirection: 'a',
      paddingSize: '2',
      marginDirection: 'a',
      marginSize: '2',
      playgroundText: 'Use the controls above to try out the different spacing helpers'
    }
  },
  computed: {
    computedPadding () {
      return `p${this.paddingDirection}-${this.paddingSize}`
    },
    computedMargin () {
      return `m${this.marginDirection}-${this.marginSize}`
    }
  }
}
</script>

<style scoped>
.spacing-playground .v-select .v-input__prepend-outer, .spacing-playground .v-select .v-input__append-outer{
  margin-top: 0.55rem;
  margin-right: 0.2rem;
}
</style>
```

[![Image from Gyazo](https://i.gyazo.com/4f73f7550412d1f4f45b2a94441a8ddc.png)](https://gyazo.com/4f73f7550412d1f4f45b2a94441a8ddc)

<br><br>

# Typography

すごく簡単に、色、濃さ、太さを設定できる。

```
<template>
  <div>
    <h3>Typography</h3>
    <v-card class="mt-5 mb-8">
      <v-card-text>
        //背景、text, textを濃くする。
        <h1 class="display-4 purple yellow--text text--darken-2">Heading 1</h1>
        //フォントを太く、細く。
        <h2 class="font-weight-light">Heading 2</h2>
        //フォントの色を変える。
        <h2 class="display-3 text-secondary">Heading 2</h2>
        <h3 class="display-2">Heading 3</h3>
        <h4 class="title">Title</h4>
        <h5 class="subtitle-1">Subtitle</h5>
        <p class="body-1">Body</p>
      </v-card-text>
    </v-card>
  </div>
</template>
```

[![Image from Gyazo](https://i.gyazo.com/70855be5c89d886d895d560ac618fe77.png)](https://gyazo.com/70855be5c89d886d895d560ac618fe77)

https://github.com/kazumawada/vuetify-basic-components







