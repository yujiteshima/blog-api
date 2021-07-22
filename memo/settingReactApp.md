# Setting React App
Yuji Teshima

## Reactの環境構築の覚書
create-react-appしてLinterをセッティングして、様々な記事や書籍を見様見真似で、
環境構築するが、create-react-appした初期の状態でエラー真っ赤となり、動かして学ぶ前につまずくことが多いのではないか。

様々な記事を確認し、調査して環境構築についての知見をまとめていきたい。

## ESLintとは
ESLintはJavaScriptの静的検証ツールである。
検証ルールはon/offできる。
カスタムルールを作成できる。
ビルトインルールがある。
プラグインがたくさん公開されてる。

## 設定ファイル
設定ファイルは幾つかの形式をサポートしている
個人的には、コメントを使えるか使えないかが大きい差のように感じる。
- .eslintrc.js // コメント使える
- .eslintrc.yaml #コメント使える
- .eslintrc.json  コメント使えない
- package.jsonファイルにeslintConfigプロパティを作成して定義　コメント使えない

```
your-project
├── .eslintrc.json
├── lib
│ └── source.js
└─┬ tests
  ├── .eslintrc.json
  └── test.js

your-project
├── package.json
├── lib
│ └── source.js
└─┬ tests
  ├── .eslintrc.json
  └── test.js
```

設定ファイルは検証されるファイル自身のディレクトリにある設定ファイルの内容が、
優先される。親ファイルを継承しつつオーバーライドするイメージ。

ESLintはルートディレクトリまでの全ての親フォルダで構成ファイルを検索する。
検索を止めたいディレクトリのpackage.jsonのeslintConfigもしくは、.eslitrc.*ファイルで``` "root": true ```を設定する。するとそれ以上の親ディレクトリを検索しにいかない。

