# include
Pugにおけるincludeという機能は, 共通部分をパーツ化するためにある.  
共通パーツ化したファイルは様々な箇所で何度も呼び出せるため非常に便利である.

例として, `common/_head.pug`を`index.pug`からincludeするケースを示す.

common/_head.pug

```
head
  title サブタイトル
  script(src='js/jquery.js')
  script(src='js/app.js')
```

呼び出すときは以下のようにする.

index.pug

```
doctype html
html
  include common/_head.pug
  body
    h1 はろー！
```
