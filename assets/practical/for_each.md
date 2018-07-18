# ループ
Pugではループ処理も表現することができる.  
Pugでのループ処理にはforとeachの２種類がある.

### for

```
ul
  - for (var i = 0; i < 5; i++)
    li たかし
```

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
配列の値を順番に出力する場合はeachが便利である.

```
- var items = [ "たかし", "たけし", "かずきち" ]
ul
  each item in items
    li #{item}
```

```html
<ul>
  <li>たかし</li>
  <li>たけし</li>
  <li>かずきち</li>
</ul>
```

また, 出力は`=`で省略することができる.

```
- var items = [ "たかし", "たけし", "かずきち" ]
ul
  each item in items
    li= item
```
