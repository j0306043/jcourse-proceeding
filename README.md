# 情報コース卒業研究報告予稿集用LaTeXスタイルファイル

卒業研究報告予稿集用の原稿執筆のためのLaTeXスタイルファイルです。

# ファイルの概要

- jcourse-proceeding.sty: スタイルファイル本体。
- sample.tex: サンプルのLaTeXソース。スタイルファイルの使用例。
- sample.pdf: sample.texのコンパイル結果。予稿の出来栄えの例。

# 使い方

たいしたことはしていませんので、`sample.tex`を見れば、すぐ使えると思います。

- 予稿のLaTeXソースと同じディレクトリに、`jcourse-proceeding.sty`ファイルを置きます。
- LaTeXソースのプリアンブルに下記を書きます。
```
\usepackage{jcourse-proceeding}
```

- 発表に関するパラメタを設定します。
```
\jcpnumber{A--2--1} % 発表番号
\title{〇〇に関する研究} % 卒業研究の題目
\author{岩手　太郎} % 発表者氏名
\jcplaboratory{（岩手研究室）} % 研究室名
\jcpabstract{概要を書きます。概要をつけることは必須ではありません。} % 概要
```

# 補足説明

- 本スタイルファイルは、以下の4つを調整します。
  - `\maketitle`コマンドにより生成される題目著者等のタイトル領域
  - ページの余白
  - ページ番号の形式
- 自分の発表番号を、タイトル領域の左肩につけることになっているので、それに対応しています。ページ番号にも発表番号が付加されます。
- 対応するTeXのバージョンとしては、TeX Live 2020以降をお使いください。動作確認は、TeX Live 2020で行っています。TeX Live 2019でも動くと思いますが、動作確認していません。これよりも古いLaTeXでは動くかどうかわかりません。
- `\documentclass`のスタイルファイルには日本語用に注意深く作られたbxjsarticleを使用することを想定しています。
  - bxjsarticle使用の場合(推奨): 下記のように、`\documentclass`のオプションのLaTeXエンジン指定に`autodetect-engine`を指定しておけば、LaTeXエンジンが自動判定され、pLaTeX+dvipdfmx, LuaLaTeX, XeLaTeX, pdfLaTeXどれでも行けると思います。補足ですが、`jbase=13.35Q`は和文フォントサイズを9.5ptにする指定です。おおよそ和文フォントの単位(Q:級)では、13.35Q=9.5ptです。
  ```
  \documentclass[autodetect-engine,dvi=dvipdfmx,ja=standard,twocolumn,jbase=13.35Q]{bxjsarticle}
  ```
  - jsarticle使用の場合(非推奨): pLaTeX+dvipdfmxの人でどうしてもjsarticleにしなければならない場合、下記のように`\documentclass`を宣言することで従来のjsarticleでも行けると思いますが、推奨しません。英語のみの論文であれば、article(jsなし)でも大丈夫です。
  ```
  \documentclass[twocolumn]{jsarticle}
  ```
