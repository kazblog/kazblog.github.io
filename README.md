# kazumawada.github.io

Ruby
Gem
Gem install jetyll bundler

jekyll new blog
作ったファイルのディレクトリに移動。
bundle exec jekyll serve
ローカルにサイト(http://127.0.0.1:4000/)が表示される。

_draftフォルダをrootディレクトリに作ったら、ブラウザに表示されず、ファイルを格納しておくことができる。
$  jekyll serve —drafts
これでブラウザに下書きが表示されている。



フォルダを見て見る
_siteは、自分が操作するものではなく、ブログを更新するたびに自動でアップデートしてくれる。


画像で絶対パス(![言葉](url))を使うと、ローカルでは動いていたが、github pagesにpushしたら見れなくなった時の対処法がここに書かれている。
https://github.com/mkdocs/mkdocs/issues/1757
/blogが入んないんだよな。github.ioにpushするか？そうすれば画像がワークする。


githubにpush時に大事なこと
Config.ymlのbaseurlには、githubで作ったレポジトリの名前。今回僕はblogだったので、それを記入します。


jekyll serve
git init
git checkout -b blog_branch

git status
git add .
git commit -m "Initial commit"

 git remote add origin https://github.com/kazumawada/blog.git
git push origin blog_branch


疑問

ekyllのサムネイルどうやってんだろ。

記事の編集方法。更新方法。
予想: cloneして編集して、またpush。
結果：ghから、$ git clone urlして手元にクローン。そこからまた$ jekyll serveで編集。そしてpush。
参考：https://qiita.com/nt_tn/items/c5ea999a2638e03ee418

jekyllのcssはここ。
https://stackoverflow.com/questions/45769857/css-to-add-to-jekyll-minima-not-completely-override-it


有益ページ
http://jekyllrb-ja.github.io/docs/posts/  ここに画像の挿入の仕方、タグが書かれている。
http://jekyllrb-ja.github.io/docs/plugins/ プラグイン
