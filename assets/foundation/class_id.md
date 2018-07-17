# クラスとID

`id=""` `class=""`を省略して書ける.  
タグのすぐ後に、`#id名` `.class名`を付けて利用する.  
`div` は省略する.

Pug
```html
#main
  h1.title タイトル
  p.msg ほげほげ
```

HTML
```html
<div id="main">
  <h1 class="title">タイトル</h1>
  <p class="msg">ほげほげ</p>
</div>
```