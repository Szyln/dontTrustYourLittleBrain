## Primitive Coercion 將原始資料類型強制改成物件來用
>[Coercion 強迫](Coercion%20強迫.md)

```js
// 前者.後者：後者是前者的屬性，所以可以點
// 那原始資料都是傳值，哪來的屬性？？？
let str = 'Hello'
str.method
```

JS 可以強迫把原始資料類型改成 object 來使用（比如說使用 `.length`功能）

### 正常的作法
JS 直接讀取就可以了
```js
let str = "Hello";
cosole.log(type str); // log string
cosole.log(str.toLowerCase()); // log hello

```

### 不正常的作法（不推薦）
- 使用 new String() 的方式生成 object，再去讀取 object 的功能但會佔記憶體，吃效能
>JS 有 [Coercion 強迫](Coercion%20強迫.md) 的特性，==不需要這樣處理==
```js
let str = new String("Hello");
cosole.log(type str); // log object
```