---
title: "Function"
tag: 
- js/function
---
## 函式 function
一種物件
```js
// function declaration
function 名稱(parameter) {
 功能(parameter);
}

// invoke(執行)
名稱(argument);
```

寫程式的時候，會遇到好幾句程式碼才能完成一個動作的時候，這時候可以製作 function
來將繁複繁複的程式碼整理成一個功能，增加重複利用性、可讀性、方便使用性

- 參數
- 功能的內容

---

### 目錄
- [console.log](JavaScript/資料類型/Function/console.log.md)
- [函式表達式 function expression](JavaScript/資料類型/Function/函式表達式%20function%20expression.md)
- [Higher Order Function](JavaScript/資料類型/Function/Higher%20Order%20Function.md)
- [IIFE](JavaScript/資料類型/Function/IIFE.md)

#### this 
- [this](JavaScript/資料類型/Function/this.md)
- [4.箭頭函式 arrow function](JavaScript/資料類型/Function/4.箭頭函式%20arrow%20function.md)
- [置換函式的 this 指向](JavaScript/資料類型/Function/置換函式的%20this%20指向.md)

##### 參數
- [預設參數](JavaScript/資料類型/Function/預設參數.md)
- [其餘參數 Rest Parameters](JavaScript/資料類型/Function/其餘參數%20Rest%20Parameters.md)
- [函式的隱藏的參數](JavaScript/資料類型/Function/函式的隱藏的參數.md)



  


## return 或是 console.log
-   function 執行之後，若要將執行後的結果儲存於變數中，要用 `return`
-   單純顯示可直接用 `console.log`，除 bug 好用

## 判斷終止 return 或 }
### return 一旦碰到第一個 return 就會跳出整個 function
也可以 
```js
function fun(x) {
	return;
}
```
不回傳東西當做終止 function 用

### } 沒有碰到 return 就會執行到 function 的結尾 }

## [[函式表達式 function expression]]
## 原生 function
### alert
```js
alert('你好');
```
#### prompt
彈出式視窗輸入框
```js
prompt('請輸入年齡');
```
#js #function