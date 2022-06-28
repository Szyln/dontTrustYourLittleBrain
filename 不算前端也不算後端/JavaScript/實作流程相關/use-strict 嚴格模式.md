---
title: "use-strict 嚴格模式"
tag: 
- 
---
# 嚴格模式 use strict
>[JavaScript 的嚴格模式 "use strict"](https://ithelp.ithome.com.tw/articles/10191736)

使撰寫語法的時候，如果用了不嚴謹的寫法，會跳出錯誤提示

> 可以解決[全域污染](全域污染.md)問題


### 常見的錯誤：
-   不宣告直接賦予變數
-   刪除已經宣告的錯誤
-   物件內有重複屬性
-   數值使用 8 進位語法
-   不能使用 'with' 語法
-   arguments、eval 不能作為變數名稱
-   新增的保留字也不能被作為變數名稱 implements, interface, let, package, private, protected, public, static, yield，這些是為了 ES6 做得準備。

## 使用方法
### 在全域下
```js
// 在全域直接寫
'use-strict';

// 開始寫程式碼
```

### 在 [[Function]] 下
```js
function fn() {
	'use-strict';
	
	// 開始寫 function 內容
}
```


