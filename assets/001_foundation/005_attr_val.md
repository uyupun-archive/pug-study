# 属性と値
ある要素に対して属性と値を指定する場合, `要素名(属性='値')`の形式で記述する.

> Pug
```
a(href='https://oic.ac.jp' target='_blank') OIC
img(src='img/しげる.jpg')
```

これをHTMLに変換すると以下のようになる.

> HTML
```html
<a href="https://oic.ac.jp" target="_blank">OIC</a>
<img src="img/しげる.jpg">
```
