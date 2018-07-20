# コンパイル
Pugはそのままブラウザで動作することはできないため, Pugで記述されたファイルはHTMLにコンパイルする必要がある.  
そのため, 今回はGulpを使ってPugからHTMLの変換を自動化する.

Gulpで実行したいタスクは, `gulpfile.js`に記述する.  
以下のコマンドで`gulpfile.js`を作成する

```bash
$ touch gulpfile.js
```

次に, お好きなエディタで以下のコードを記述してほしい.  

```js
const gulp = require('gulp')
const pug = require('gulp-pug')

// Pugのコンパイル
gulp.task('pug', () => {
  gulp.src([ './assets/pug/*.pug', '!./assets/pug/_*.pug' ])
      .pipe(pug({ pretty: true }))
      .pipe(gulp.dest('./public/'))
})

// Pugの自動コンパイル
gulp.task('watch', [ 'pug' ], () => {
  const watcher = gulp.watch('./assets/pug/*.pug', [ 'pug' ])
  watcher.on('change', event => {})
})
```

細かいNode.jsの文法の解説は省略するが, Gulpでは基本的に`const 変数名 = require('パッケージ名')`で必要なパッケージを読み込み, `gulp.task()`の中にそれぞれのタスクを記述する.  
また, タスク内の処理と処理をつなぐ場合は`pipe()`を用いる.

`gulp.src([ './assets/pug/*.pug', '!./assets/pug/_*.pug' ])`のうち, `'./assets/pug/*.pug'`はコンパイルするPugファイルの指定, `'!./assets/pug/_*.pug'`はコンパイル対象から除外するPugファイルの指定である.  
この場合, `'!./assets/pug/_*.pug'`は先頭に`_`のあるファイルを除外していることになる.

`pug({ pretty: true })`はコンパイル後のHTMLを整形して出すという設定である.  
`false`にした場合, スペースなどが圧縮されたHTMLが生成される.

`gulp.dest('./public/')`はコンパイル後のHTMLファイルの作成先である.

次に, Pugファイルを作成し, 実際にコンパイルしてみよう.

```bash
$ mkdir -p assets/pug/
$ echo p ぅゅ... > assets/pug/index.pug
$ gulp pug
[15:56:14] Using gulpfile ~/Desktop/pug-test/gulpfile.js
[15:56:14] Starting 'pug'...
[15:56:14] Finished 'pug' after 6.64 ms
```

コンパイルされているかどうか, 確認する.

```bash
$ cat public/index.html
<p>ぅゅ...</p>
```

最後に, 自動コンパイルを試す.  
まず, ターミナルを２つ立ち上げ, それぞれ`pug-test`ディレクトリへ移動する.  

```bash
$ cd pug-test
```

片方のターミナルで, 以下のコマンドを実行し, Pugの自動コンパイルをするタスクを実行する.

```bash
$ gulp watch
[03:31:18] Using gulpfile ~/Desktop/pug-test/gulpfile.js
[03:31:18] Starting 'pug'...
[03:31:18] Finished 'pug' after 6.72 ms
[03:31:18] Starting 'watch'...
[03:31:18] Finished 'watch' after 7.62 ms
```

もう片方は, Pugファイルを変更する.

```bash
$ echo h1 ぷんぽぷんぽ > assets/pug/index.pug
```

Pugの自動コンパイルを実行している方のターミナルを確認すると, 自動でコンパイルされていることが分かる.

```bash
$ gulp watch
[03:31:18] Using gulpfile ~/Desktop/pug-test/gulpfile.js
[03:31:18] Starting 'pug'...
[03:31:18] Finished 'pug' after 6.72 ms
[03:31:18] Starting 'watch'...
[03:31:18] Finished 'watch' after 7.62 ms
[03:31:34] Starting 'pug'...
[03:31:34] Finished 'pug' after 1.83 ms
```

```bash
$ cat public/index.html
<p>ぷんぽぷんぽ</p>
```
