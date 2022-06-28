## Global Scope
在 Global 宣告的變數與函式，在哪裡都可以讀取
```js
// 誰都可以調用 Global 宣告的變數
var age = 14;
let name = "Sam";
const height = 150;

// 誰都可以調用 Global 宣告的 Function
function myName() {
	console.log(name);
}

myName();		// log "Sam"
```