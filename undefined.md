## undefined
已宣告尚未賦值，也是一種值

> 不要自己設定變數的值是 `undefined`，需要的話可以設定 [Null](Null.md)
^70b77e

- `const` 不一定有值，而且不可能是 `undefined`（必須賦值）
	- 該作用域中存在使用後宣告：[暫時性死區(TDZ)](暫時性死區(TDZ).md)，炸掉
	- 該作用域是有使用前宣告：以這個作用域的宣告為準，必須賦值
	- 該作用域只有使用：外層宣告的值，必須賦值
	- 該作用域重複宣告：炸掉
- `let` 不一定有值，預設也不一定
	- 該作用域中存在使用後宣告：[暫時性死區(TDZ)](暫時性死區(TDZ).md)，炸掉
	- 該作用域是有使用前宣告：以這個作用域的宣告為準，預設 `undefined`
	- 該作用域只有使用：外層宣告的值，預設 `undefined`
	- 該作用域重複宣告：炸掉
- `var` 一定有個值，預設是 `undefined`


### let 表格版
> [let](let.md)

![](let.md#^8b4b01)
### const 表格版
>[const](const.md)

![](const.md#^015b6b)



```js
// var, let, const
var a;			// undefined
let b;			// undefined
const c;		// 禁止未賦值，炸掉
console.log(a)
console.log(b)
console.log(c)
```
```js
var a;
console.log(a)
var a = 1

// undefined 不會炸
```
