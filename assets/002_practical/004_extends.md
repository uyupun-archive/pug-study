# extends
Pugでは同じようなレイアウトのページを量産する際に便利なextendsという機能が用意されている.

まず, 以下のようにレイアウトのベースになるファイルを作成する.

> Pug: common/_layouts.pug
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
例として, `common/_layouts.pug`を基に, `first.pug`と`second.pug`という２つのファイルを作成する.

> Pug: first.pug
```
extends common/_layouts.pug
block title
  title １ページ目
block content
  h1 これは１ページ目です
```


> Pug: second.pug
```
extends common/_layouts.pug
block title
  title ２ページ目
block content
  h1 これは２ページ目です
```

これをHTMLに変換すると以下のようになる.

> HTML: first.html
```html
<!DOCTYPE html>
<html>
  <head>
    <title>１ページ目</title>
  </head>
  <body>
    <h1>これは１ページ目です</h1>
  </body>
</html>
```

> HTML: second.html
```html
<!DOCTYPE html>
<html>
  <head>
    <title>２ページ目</title>
  </head>
  <body>
    <h1>これは２ページ目です</h1>
  </body>
</html>
```
