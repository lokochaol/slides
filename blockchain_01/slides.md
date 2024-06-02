---
layout: cover
---

# Slidev

Slidevで本質的な内容の作成に集中する

---
layout: center
background: /background-1.png
class: 'text_white'
---

<!-- - layoutは"---"の後に改行を入れないで中に記述して囲うことでかける👍
- This is a page with the layout `center` and a background image. -->
# 目次

- なぜSlidevを使うのか？
- インストール
- できること
- 基本となる書式

---

# なぜSlidevを使うのか

<!-- This is a default page without any additional metadata. -->

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ホームページプレビュー埋め込み</title>
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
    <style>
        /* 16:9のアスペクト比を保つためのスタイル */
        .aspect-ratio-16-9 {
            position: relative;
            width: 100%;
            padding-bottom: 56.25%; /* 16:9 のアスペクト比 */
        }
        .aspect-ratio-16-9 iframe {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            border: none; /* 枠を消す */
        }
    </style>
</head>
<body class="bg-gray-100 flex justify-center items-start min-h-screen">
    <div class="bg-white shadow-lg rounded-lg overflow-hidden max-w-4xl w-full">
        <div class="aspect-ratio-16-9">
            <iframe src="https://sli.dev/guide/why"></iframe>
        </div>
    </div>
</body>
</html>

---

# 前準備

空のslidev環境を作成する

- 環境を作る

```shell
$ npm install @slidev/cli @slidev/theme-default
```

- slides.mdを作成し、内容を記述していく

```shell
$ touch slides.md
```

- slidevのローカルサーバーを立ち上げる

```shell
$ npx slidev
```

---

# Slidev

Slidevに関する基本的な情報をまとめておく

- slidev公式ページ
  https://sli.dev/
- テーマたち
  https://sli.dev/themes/gallery

---

# Markdownでコマンドラインの実行と結果のハイライト

Markdownでshellのコマンドをハイライトしたい時

ハイライトなし

```
$ ls
```

ハイライト

```shell
$ ls
```

---

# どうやって使うのがベストだろうか？

自由自在に使うためには必要なハードルが高そうなので、必要に応じてdocsを読んでこの記事にまとめる形で自由自在に使えることを目指す。

- Windi CSS や Vue componetsが使えるらしいが一旦これらの勉強はしない
- akiyokoさんのspeaker deckのような形で毎日学んだことをアウトプットの形で起こしていく
  https://speakerdeck.com/akiyoko

---

# Page 3

とりあえずチュートリアルを一通り進める

You can directly use Windi CSS and Vue components to style and enrich your slides.

<div class="p-3">
  <Tweet id="20" />
</div>
