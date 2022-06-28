## Function Scope
Function Scope 裡面宣告的變數與函式，只能在函式內使用
```js
function myName() {
	// 只有這個 Function 可以使用
	var age = 14;
	let name = "Sam";
	const height = 150;
	
	console.log(`${age}, ${name}, ${height}`); // log 14, Sam, 150
}

myName();			// log 14, Sam, 150
console.log(name);	// error
```
