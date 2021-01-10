# kazumawada.github.io

いちいちかくページを見るのは、めんどくさい。一ページで全部観れるのをトップに固定して作りたいな。

変数
http://jekyllrb-ja.github.io/docs/variables/


固定ページはこうやって作れる。

<!DOCTYPE html>
<html lang="{{ page.lang | default: site.lang | default: "en" }}">

  {%- include head.html -%}

  <body>

    {%- include header.html -%}



    <main class="page-content" aria-label="Content">
      <div class="wrapper">
      p 固定記事 /p
        <h1 class="text-center">
        <a href="http://localhost:4000/docker-cheatsheet">ポートフォリオ作成までの全過程</a>
        </h1>

        {{ content }}
       
      </div>
    </main>
