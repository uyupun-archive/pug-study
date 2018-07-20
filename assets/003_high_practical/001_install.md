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
`npm init`時に色々と聞かれるが, 今回は全てエンターで良い.

```bash
$ npm init
This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sensible defaults.

See `npm help json` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg>` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
package name: (test)
version: (1.0.0)
description:
entry point: (index.js)
test command:
git repository:
keywords:
license: (ISC)
About to write to /Users/tyokinuhata/Desktop/pug-test/package.json:

{
  "name": "pug-test",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "Kazukichi <kazukiti201@gmail.com> (https://tyokinuhata.github.io/portfolio/)",
  "license": "ISC"
}
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
