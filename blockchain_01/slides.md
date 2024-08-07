---
layout: cover
---

# ブロックチェーン技術について
東大公開講座での学習をもとに自分なりにまとめなおし定着させることを目的とする。また、ブロックチェーンの社会的に有意義な使い道を探る。

---

# ビットコインのデータがいかに扱われているか

## エンコード方式: base58
ビットコインで使うために開発されたエンコード方式

**ブロックチェーンのデータにミスがあっては困る**
- base64に比べ間違いやすい文字が省かれている
- base58check: 転写ミスを防ぐための仕組み

---

# エンコードとは？暗号化とどう違う？
そもそもエンコードって
https://wa3.i-3-i.info/word135.html

>バイナリデータをテキストデータで扱えるように特定のルールに従って変換すること

---

# Base58 Check encoding
アルゴリズムを見てみる

```python
ALPHABET = "123456789ABCDEFGHJKLMNPQRSTUVWXYZabcdefghijkmnopqrstuvwxyz"

def convertToBase58(num):
    sb = ''
    while (num > 0):
        r = num % 58
        sb = sb + ALPHABET[r]
        num = num // 58;
    return sb[::-1]

s = 25420294593250030202636073700053352635053786165627414518
b = convertToBase58(s)
print("%-56d -> %s" % (s, b))

hash_arr = [0x61, 0x626262, 0x636363, 0x73696d706c792061206c6f6e6720737472696e67, 0x516b6fcd0f, 0xbf4f89001e670274dd, 0x572e4794, 0xecac89cad93923c02321, 0x10c8511e]
for num in hash_arr:
    b = convertToBase58(num)
    print("0x%-54x -> %s" % (num, b))
```

---

# sb[::-1]
これなんの処理だっけ？

開始index:終了index:パターン？


---
layout: fact
---

>まず、Bitcoinはもっとも根本的なレベルで世界中の何千人もの研究者の20年に及ぶ暗号通貨と、40年に及ぶ暗号学が創り上げたコンピューターサイエンスのブレイクスルーである。

---

# ビザンチン将軍問題
>もっと一般的に、ビザンチン将軍問題はインターネットのような信頼することができないネットワーク上でお互いに知らない参加者間で信頼をどう構築するかという問題を提起している。
[なぜBitcoinが重要なのか？](https://medium.com/cryptoage/%E3%81%AA%E3%81%9C%E3%83%93%E3%83%83%E3%83%88%E3%82%B3%E3%82%A4%E3%83%B3%E3%81%8C%E9%87%8D%E8%A6%81%E3%81%AA%E3%81%AE%E3%81%8B-bac3c74e0203)

-> これに対して、ブロックチェーンは解決策を与えてくれる

---
layout: fact
---

>このブレイクスルーの影響はいくら評価しても過大評価することはないだろう。

---
layout: center
---

# 仲介者を必要としないやりとりが可能となる
そして、所有権をの正当性を検証することができる。

---

# Bitcoin Block 0 
satoshi nakamoto

https://www.blockchain.com/explorer/blocks/btc/0

---

