## Function 特有的物件屬性
- `name`：也可以沒有
- `code`：可以被執行的程式碼
- [置換函式的 this 指向](置換函式的%20this%20指向.md)：bind(), call(), apply()

> 之後會看到，沒有名稱的函式： [函式表達式 function expression](函式表達式%20function%20expression.md) > 匿名函式

```js
// function 的名稱是一個 function 的屬性 name
function fnA(param) {
	// 這裡的 code 也是 function 的屬性
	// code here
	console.log(param)
}

console.log(fnA.name)	// log fnA
```