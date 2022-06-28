### 非嚴格模式的 block 
>[全域污染](全域污染.md)

var, function 宣告不形成 [Scope 作用域](Scope%20作用域.md)，[全域污染](全域污染.md)]

```javascript
// 不推薦這樣使用

var x = 1;

{
  var x = 2;
	function fn1() {
		console.log('我有跑錯棚嗎？')
	}
}
fn1()						// log 我有跑錯棚嗎？ 全域污染
console.log(x); // 非嚴格模式的話 block 不會形成作用域，x = 2
```

