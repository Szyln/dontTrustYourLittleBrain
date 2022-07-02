## 淺層拷貝(Shallow Copy)
- 只有將最外層物件的記憶體改掉
- 如果該物件屬性中還有其他物件的話，屬性中的物件還是保有傳參考特性
- 程式碼較單純

### Object.assign()
將物件指派到新的記憶體中
```js
const newObject = Object.assign({}, originObject)
```
- 第一個 parameter 放空的 object (建立新的記憶體空間)
- 第二個放想要原有的 object（會在第一個參數的空物件中展開）

### 在新的空 object 內展開
>[展開](展開.md)
```js
const newObject2 = {
    ...originObject
}
```

### `=` 會配給物件新的記憶體
>[Assignment Operator(=)：指派、賦值、初始化](Assignment%20Operator(=)：指派、賦值、初始化.md) 
```js
let a = { a: 1 }
let b = a // link
let b = { c: 2 } // 這個是直接改變數對應的記憶體，不會跟 a 有 link 關係
```