# kazumawada.github.io

カテゴリーにtagマークをつけたい。
liの丸ぽちいらない。

いちいちかくページを見るのは、めんどくさい。一ページで全部観れるのをトップに固定して作りたいな。

変数
http://jekyllrb-ja.github.io/docs/variables/



branch01でやる事

aboutにportfolio,草 done
rspecチートシート done
カテゴリーの文字の前に、tagマークをつける。done
liの黒点入らない=liはいらない。done
学習ログを固定にすることはできないっぽいから、headerに書くことにする。

<!---------- 固定記事 ----------------->
      <div class="wrapper"><!-- これが無いと横にいっぱい伸びる -->  
      　<div class="text-center">
          　<span class="post-meta">{{ post.tags.portfolio-log | date: date_format }}</span> 
        </div>
      </div>   
  <!---------- 固定記事 ----------------->

  aboutのリストマーク done
