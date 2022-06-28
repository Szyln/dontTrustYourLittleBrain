## var 的 hoisting
var 的 hoisting 只有在**賦值之前**有效果
```javascript
console.log(a);	// 不會輸出 not defined，而是輸出 undefined 
var a = 1; 
console.log(a); // 輸出 1
```
hoisting 的效果可以解讀成
```javascript
var a; 			// hoisting
console.log(a);	// log undefined
var a = 1; 		// 賦值
console.log(a); // 輸出 1
```