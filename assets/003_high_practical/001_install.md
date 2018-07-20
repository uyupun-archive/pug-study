# インストール
この章では実際にPugを用いた小規模なプロジェクトを構築する.  
それに先立って必要なツールをインストールする.

### Node.jsとnpm
初めに, https://nodejs.org/ja/download/ からNode.jsをインストールする.  
Node.jsとは, 一言で説明するとサーバサイドで動作するJavaScriptである.

Node.jsのインストールに成功した場合, 以下のようなコマンドを入力すると,

```bash
$ node -v
v8.9.1
```

のようにバージョンが表示される筈である.

また, Node.jsをインストールすると同時にNode.jsのパッケージ管理システムであるnpm(Node Package Manager)もインストールされる.  
npmが正常にインストールされているかは, 以下のコマンドで確認する.

```bash
$ npm -v
5.6.0
```

# プロジェクトの作成
まずはディレクトリを作成し, 作成したディレクトリに移動する.

```bash
$ mkdir pug-test
$ cd pug-test
```

次に, `package.json`を生成する.  
`package.json`はnpmでインストールしたいパッケージなどを記述しておくためのファイルである.  
`package.json`の雛形は以下のコマンドで生成できる.

```bash
$ npm init
```

次に, Gulpをインストールする.  
Gulpは, Node.jsで動作するタスクランナーである.  
要するに, 面倒な作業を自動化できるツールである.

```bash
$ npm install gulp --save-dev
```

最後に, gulp-pugをインストールする.  

```bash
$ npm install gulp-pug --save-dev
```
