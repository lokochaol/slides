# Python
Pythonについて学んだことをまとめる

---
layout: center
---

# 代入では値はコピーされない
>**ミュータブル**なアイテムを含むコレクションについては、元のオブジェクトを変更せずにコピーを変更できるように、コピーが必要になる

---
layout: center
---

# ミュータブル
mutable

>ミュータブルオブジェクトは、オブジェクトを作成した後に状態を変更できるオブジェクトです。 [mdn](https://developer.mozilla.org/ja/docs/Glossary/Mutable)

---

# Pythonにおいてミュータブルな型

- 
- 



---
layout: fact
---

# 安易に代入で、思わぬところで元のデータを書き換えてしまった
変更を加えたくない値はコピーしから扱う

---
layout: center
---

# Python のコピー
copy と deepcopy

## copy
shallow "浅い" copy
xの浅いコピーを返す。
```python
copy.copy(x)
```

## deepcopy
deep "深い" copy
xの深いコピーを返す。
```python
copy.copy(x[, memo])
```

---

# 変数スコープについて
公式でまとめられている？

https://qiita.com/msssgur/items/12992fc816e6adf32cff

---

# 関数からの返り値をそのまま展開する

```python
def func() -> int, str, str:
    return 1, "a", "b"

print(*func())
```

```shell
1
a
b
```

---

# pythonの変数はブロックで束縛される
逆にglobalやunlocal定義をしない限り、ブロック内でしか束縛されない

-> ブロックとは？

---

# 文字列を安全にいじる

data.get(, "")

---

# スライスとストライド

```python
text[start:end:pattern?]
```

---

# Enum
djangoのchoicesはpythonの標準ライブラリのenumを継承している。

---

# テストデータ作成のベストプラクティス、、
現状の実装はカスタムコマンドを使ってfactoryから生成している様子。
factoryとfixtureはどう使い分ける？

---

# dict keyの欠損にも対応する実装のベストプラクティス

- get
- setdefault
- defaultdict
- __missing__

---