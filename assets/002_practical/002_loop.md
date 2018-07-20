# ループ
Pugではループを表現することができる.  
Pugでのループ処理には`for`と`each`の２種類がある.

### for

> Pug
```
ul
  - for (var i = 0; i < 5; i++)
    li たかし
```

これをHTMLに変換すると以下のようになる.

>  HTML
```html
<ul>
  <li>たかし</li>
  <li>たかし</li>
  <li>たかし</li>
  <li>たかし</li>
  <li>たかし</li>
</ul>
```

### each
配列の値を順番に出力する場合は`each`が便利である.

> Pug
```
- var items = [ "たかし", "たけし", "かずきち" ]
ul
  each item in items
    li #{item}
```

これをHTMLに変換すると以下のようになる.

> HTML
```html
<ul>
  <li>たかし</li>
  <li>たけし</li>
  <li>かずきち</li>
</ul>
```

また, `li #{item}`は`li= item`というように省略できる.

> Pug
```
- var items = [ "たかし", "たけし", "かずきち" ]
ul
  each item in items
    li= item
```
