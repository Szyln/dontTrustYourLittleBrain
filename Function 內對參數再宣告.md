## Function 內對參數再宣告
- `var`：可，[var 的 hoisting：賦值（初始化）前使用不報錯](var%20的%20hoisting：賦值（初始化）前使用不報錯.md)
- `let` 不行，[暫時性死區(TDZ)](暫時性死區(TDZ).md)

### var
var 可以重複宣告，會 hoisting，作用域內若在宣告前被呼叫，不會產生錯誤提示
```javascript
function fn(a) {
	console.log(a);	// 2.log 1
	var a = 2;		// 3.重複宣告
	console.log(a);	// 4.log 2
}
fn(1);				// 1.在外部先指定 a = 1
```

### let
let 不能重複宣告，不會 hoisting，作用域內若在宣告前被呼叫，**會**產生錯誤提示（[暫時性死區(TDZ)](暫時性死區(TDZ).md)）
```
// let 在被宣告前呼叫的話
Cannot access 'a' before initialization
```
會產生暫時性死區，不能執行
```javascript
function fn(a) {
	console.log(a);	// 2.暫時性死區，炸掉
	let a = 2;			// 歿.不可重複宣告，不能執行
	console.log(a);	// 歿.不能執行
}
fn(1);				// 1.外部指定 a = 1
```