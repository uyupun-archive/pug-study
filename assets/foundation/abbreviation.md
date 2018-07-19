# 省略記法

ネストする時, 改行とインデントを省略して記入することができる.  
タグの後に, スペースを入れ, `:` を入れることでネストすることができる.  
2回以上, 使用することも可能だが, テキストの後に使用することはできない.  
`nav` などで使用すると便利.  

Pug
```html
ul
  li: a(href="#") ほげほげ
  li: a(href="#"): span ぴよぴよ
  li: a(href="#"): img(src="images/sample.png")
```

HTML
```html
<ul>
  <li><a href="#">ほげほげ</a></li>
  <li><a href="#"><span>ぴよぴよ</span></a></li>
  <li><a href="#"><img src="images/sample.png"></a></li>
</ul>
```