# include
Pugにおけるincludeという機能は, 共通部分をパーツ化するためにある.  
共通パーツ化したファイルは様々な箇所で何度も呼び出せるため非常に便利である.

例として, `common/_head.pug`を`index.pug`からincludeするケースを示す.

> Pug: common/_head.pug
```
head
  meta(charset='utf-8')
  title 世界に挨拶
```

呼び出すときは以下のようにする.

> Pug: index.pug
```
doctype html
html
  include common/_head.pug
  body
    h1 はろー！
```

これをHTMLに変換すると以下のようになる.

> HTML
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>世界に挨拶</title>
  </head>
  <body>
    <h1>はろー！</h1>
  </body>
</html>
```
