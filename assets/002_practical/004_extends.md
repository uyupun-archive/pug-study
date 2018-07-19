# Extends
Pugでは同じようなレイアウトのページを量産する際に便利なExtendsという機能が用意されている.

まず, 以下のようにレイアウトのベースになるファイルを作成する.

_layouts.pug

```
doctype html
html
  head
    block title
      title ページのタイトル
  body
    block content
```

ファイルごとに違うコンテンツを入れたい部分は`block 名前`で囲っておく.

例として, `_layouts.pug`を基に, `first.pug`と`second.pug`という２つのファイルを作成する.

first.pug

```
extends _layouts.pug

block title
  title １ページ目
block content
  h1 これは１ページ目です
```

second.pug

```
extends _layouts.pug

block title
  title ２ページ目
block content
  h1 これは２ページ目です
```
