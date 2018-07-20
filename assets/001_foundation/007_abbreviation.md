# ネストの省略記法
ネストする際に, 要素名の直後に`:`と半角スペースを入れることで, 改行とインデントを省略することができる.  
２回以上使用することも可能だが, テキストの後に使用することはできない.  

> Pug
```
ul
  li: a(href='#') んにゃぴ
  li: a(href='#'): span ぷんぽ
  li: a(href='#'): img(src='img/しげる.jpg')
```

これをHTMLに変換すると以下のようになる.

> HTML
```html
<ul>
  <li><a href="#">んにゃぴ</a></li>
  <li><a href="#"><span>ぷんぽ</span></a></li>
  <li><a href="#"><img src="img/しげる.jpg"></a></li>
</ul>
```
