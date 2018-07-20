### プロジェクトの作成

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

# コンパイル

Pugをコンパイルするために, `gulpfile.js` を作成する.  
`gulpfile.js` は様々な作業をまとめて処理するためのファイルである.

まず, `touch` コマンドでファイルを作成し, ファイル内にコードを記述する.

```bash
$ touch gulpfile.js
$ vim gulpfile.js
```
Vim は vi から派生し, 発展した高機能なテキストエディタだ.  
Vim は `i` キーを入力することで挿入モードになり, 文字を打つことができる.  
また, `esc` キーを入力することでコマンドモード（初期状態）に戻り, `:wq` または `ZZ` で上書き保存し, im を終了することができる.  

> gulpfile.js
>
>```js
>const gulp = require('gulp')
>const pug = require('gulp-pug')
>
>// Pugのコンパイル
>gulp.task('pug', () => {
>  gulp.src([ './assets/pug/*.pug', '!./assets/pug/_*.pug' ])
>      .pipe(pug({ pretty: true }))
>      .pipe(gulp.dest('./public/'))
>})
>
>// Pugの自動コンパイル
>gulp.task('watch', [ 'pug' ], () => {
>  const watcher = gulp.watch('./assets/pug/*.pug', [ 'pug' ])
>  watcher.on('change', event => {})
>})
>```

`!./assets/pug/_*.pug` このコードを記述することで, ファイルの先頭に `_` のあるPugファイルはコンパイルされないようになる.  

次に, Pugファイルを作成し, コンパイルする.

```bash
$ mkdir -p assets/pug/
$ echo h1 hogehoge > assets/pug/index.pug
$ gulp pug
```

コンパイルされているかどうか, 確認する.

```bash
$ cat public/index.html
```

最後に, 自動コンパイルを試す.  
まず, ターミナルを2つ立ち上げ, 2つとも `pug-test` ディレクトリへ移動する.  

```
$ cd pug-test
```

片方のターミナルで, 以下のコマンドを実行し, ファイルの変更を監視する.

```
$ gulp watch
[03:31:18] Using gulpfile ~/Desktop/pug-test/gulpfile.js
[03:31:18] Starting 'pug'...
[03:31:18] Finished 'pug' after 6.72 ms
[03:31:18] Starting 'watch'...
[03:31:18] Finished 'watch' after 7.62 ms
```

もう片方は, Pugファイルを変更する.

```
$ echo h1 piyopiyo > assets/pug/index.pug
```

`watch` している方のターミナルを確認すると, 自動でコンパイルされたことが分かる.

```
$ gulp watch
[03:31:18] Using gulpfile ~/Desktop/pug-test/gulpfile.js
[03:31:18] Starting 'pug'...
[03:31:18] Finished 'pug' after 6.72 ms
[03:31:18] Starting 'watch'...
[03:31:18] Finished 'watch' after 7.62 ms
[03:31:34] Starting 'pug'...
[03:31:34] Finished 'pug' after 1.83 ms
```
