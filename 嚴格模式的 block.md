### 嚴格模式的 block
```javascript
'use strict'

let x = 1;

{
  let x = 2;
	function fn1() {
		console.log('我有跑錯棚嗎？')
	}
}
fn1()						// undefined 沒有全域污染
console.log(x); // 嚴格模式下，使用 let 會形成作用域，x = 1 
```