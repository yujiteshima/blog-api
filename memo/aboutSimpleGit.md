# simple-gitについて

node projectの中で、gitを操作したい。
具体的には、blogサイトを作成する際に、新しいファイルを作成してgithubにプッシュした際に、
github Actionsでhookして、firebase functionsを叩く。
その際にsimple-gitでgithubの文書管理フォルダ内の全てのファイルをクローンしてくる。
一時フォルダに配置して、メタ情報付きのマークダウンをjsonに変換して、ストレージに突っ込む。
html化するときに、コードブロックをハイライトする。
メタ情報に新規、更新、削除、処理済み等が分かるフラグを持たしておけば、全てをストレージに入れなくても、新規と更新したものに限定できる。ストレージに入れたものは、処理済みフラグをオンにしてプッシュするのはどうか。
ストレージの設計は考えなくてはならない。
```
$ npm init -y
```

```
# tsconfig.json を準備する
cat <<EOL > tsconfig.json
{
  "compilerOptions": {
    "target": "esnext",
    "module": "commonjs"
  }
}
EOL
```