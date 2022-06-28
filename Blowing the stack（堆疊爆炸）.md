## Blowing the stack（堆疊爆炸）

```js
// 範例， function 呼叫自己，導致 stack 充滿要執行的 function 到爆炸
function foo() {
	return foo();
}
foo();
```