---
title: "Object"
tag: 
- js/object
---
## 物件 Object
- 屬性(properties) 的集合
- 屬性是一個：[Key-Value Pair](Key-Value%20Pair.md) 
	- 值 value 可以是任何[資料型別](資料型別.md)
		- 值是 `function` 的時候則叫做 `method`
	- 另外在 ES6 有規範了 [Method 簡寫語法糖](Method%20簡寫語法糖.md)
- [Function](Function.md), [Array](Array.md) 都是一種 Object


```js
let home = {
	name : 'Mary',
	key : value,
	properties,
	method,
}
```

---

### 目錄
- [物件的傳參考特性](物件的傳參考特性.md)

#### 操作
- [新增物件](新增物件.md)
- [改變 Mutate](改變%20Mutate.md) ^cd576c
	- C: [物件新增屬性](物件新增屬性.md)
	- R: [物件讀取屬性](物件讀取屬性.md)
	- U: [修改物件屬性](修改物件屬性.md)
	- D: [刪除整個物件](刪除整個物件.md)



#### 語法糖
- [物件內的物件簡寫語法糖](物件內的物件簡寫語法糖.md)
- [展開](展開.md)
- [從物件中提取屬性到變數中 Destructing an object](從物件中提取屬性到變數中%20Destructing%20an%20object.md)

####

- [Window Object](Window%20Object.md)
- [Storage](Storage.md)

- [物件不要傳參考的時候：深層、淺層拷貝](物件不要傳參考的時候：深層、淺層拷貝.md)
	- [淺層拷貝(Shallow Copy)](淺層拷貝(Shallow%20Copy).md)
	- [深層拷貝：暴力取消傳參考特性](深層拷貝：暴力取消傳參考特性.md)
- [讓 JSON（或是字串格式） 與 JS 讀得懂彼此：格式轉換](讓%20JSON（或是字串格式）%20與%20JS%20讀得懂彼此：格式轉換.md)

- [Destructing Assignment](Destructing%20Assignment.md)