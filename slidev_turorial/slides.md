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

---

# Code Blocks

```python
print("Hello, World!")
```

---

# Line Highliting
行ごとに強調する
```ts {2,3}
function add(
  a: Ref<number> | number,
  b: Ref<number> | number
) {
  return computed(() => unref(a) + unref(b))
}
```
```ts {2-3|5|all}
function add(
  a: Ref<number> | number,
  b: Ref<number> | number
) {
  return computed(() => unref(a) + unref(b))
}
```
ハイライトを遷移させる
```ts {hide|none|2|3|4}
function add(
  a: Ref<number> | number,
  b: Ref<number> | number
) {
  return computed(() => unref(a) + unref(b))
}
```

---

# Line Numbers
行番号の表示

```ts {6,7}{lines:true, startLine:5}
function add(
  a: Ref<number> | number,
  b: Ref<number> | number
) {
  return computed(() => unref(a) + unref(b))
}
```

# Max Height
コードブロックがスライド収まらない時、max heightを設定し、スクロール可能にできる
```ts {2|3|7}{maxHeight:'100px'}
function add(
  a: Ref<number> | number,
  b: Ref<number> | number
) {
  return computed(() => unref(a) + unref(b))
}
/// ...as many lines as you want
const c = add(1, 2)
```


---

# Two Slash Integration
TypeScript などのコードベースで利用する際に、//によるヒント表示が可能
これすごいけど多分使わない。

```ts twoslash
import { ref } from 'vue'

const count = ref(0)
//            ^?
```

---

# Shiki Magic Move
`md magic-move`として中に複数のcodeブロックを作成すると状態がスムースに遷移する
見ていてい気持ちがいい

````md magic-move
```js
console.log(`Step ${1}`)
```
```js
console.log(`Step ${1 + 1}`)
```
```ts
console.log(`Step ${3}` as string)
```
````

````md magic-move {at:4, lines: true}
```js {*|1|2-5}
let count = 1
function add() {
  count++
}
```

Non-code blocks in between as ignored, you can put some comments.

```js {*}{lines: false}
let count = 1
const add = () => count += 1
```
````

---

# Monaco Editor
`ts {monaco}`とすることで editor として開ける

```ts {monaco}
console.log('HelloWorld')
```
# Monaco Diff Editor
`ts {monaco-diff}`とすることで 差分editor も利用可能

```ts {monaco-diff}{maxHeight:'100px'}
console.log('Original text')
~~~
console.log('Modified text')
```

---

# Monaco Runner
コードの実行もできちゃうの？！もしかして、、

`{monaco-run}`コードの実行

```ts {monaco-run}{maxHeight:'100px'}
function distance(x: number, y: number) {
  return Math.sqrt(x ** 2 + y ** 2)
}
console.log(distance(3, 4))
```

`{autorun:false}`自動実行をfalseに設定する
```ts {monaco-run} {autorun:false}
console.log('Click the play button to run me')
```

---

`{showOutputAt:'+1'}` 1click後に表示
```ts {monaco-run} {showOutputAt:'+1'}
console.log('Shown after 1 click')
```


---

# 2024/6/2 できるようになったこと
進捗: https://sli.dev/guide/syntax#static-assets

- slidev の空プロジェクト作成
- 基本的な記述法

# これからやりたいこと
色々たくさん

- このチュートリアルを終わらせる
- テンプレートを使いこなせるようにする
- ブログとして機能するようにすること
  - SPA化する
