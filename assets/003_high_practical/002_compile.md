# コンパイル

```bash
$ mkdir pug-test
$ cd pug-test
$ npm init
$ npm i gulp --save-dev
$ npm i gulp-pug --save-dev
$ touch gulpfile.js
$ vim gulpfile.js
$ mkdir assets/pug/
$ cd assets/pug/
$ touch index.pug
$ echo h1 hogehoge > index.pug
$ cd ../../
$ gulp pug (or gulp watch)
~確認~
$ cd public
$ ls
$ cat index.html
```

> gulpfile.js

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