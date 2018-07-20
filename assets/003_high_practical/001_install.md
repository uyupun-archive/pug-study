# インストール

初めに, [Node.js](https://nodejs.org/ja/download/) をインストールする.  
Node.js は, サーバサイドで動くJavaScriptである.

npm 等をインストールする前にディレクトリを作成する.  

```bash
$ mkdir pug-test
$ cd pug-test
```

まず最初に, npm をインストールする.  
npm は, パッケージ管理システムの1種である. 正式名称は, Node Package Manager で Node.js のパッケージを管理する.

```bash
$ npm init
$ npm install (npm i)
```

次に, Gulp をインストールする.  
Gulp は, Node.js をベースとしたビルドシステムヘルパーである. Gulp を使用すれば, 様々な作業を自動化することができる.

```bash
$ npm i gulp --save-dev
```

最後に, Pug をインストールする.  
冒頭でも説明したように, Pug は効率的に HTML を記述するためのテンプレートエンジンだ.  

```bash
$ npm i gulp-pug --save-dev
```
