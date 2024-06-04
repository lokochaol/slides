# Backendの知識の整理
知らないことばっかりなので。いいなと思う度にここにまとめていく。

---

# jsonでschemaを書く
carcloudの実装に学ぶ

👍
- 1度の定義でバリデーション、openAPIと使いまわせる。
    -> これだけでもかなり有意義

❔
- どうやってAPI定義やバリデーションに利用している？

---

# fixtureの扱いのベストプラクティスを探る
テストデータの再利用可能性、factoryとの違い等を考えたい

---

# Generate fixture from Created DB

- 特定のモデルからパスを指定してfitureを作成するコマンドはこれ。
```shell
python manage.py dumpdata myapp.MyModel --output=myapp_mymodel_fixture.json
```
https://chatgpt.com/share/48be98da-b12e-490d-99d5-437deeb11e15

- 読み込むときは -> 複数のときはシェルスクリプト書く？ dockerで自動化するには？
```shell
python manage.py loaddata myapp1/fixtures/myapp1_fixture.json
```

---

