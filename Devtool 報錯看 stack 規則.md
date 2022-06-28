### Devtool 報錯看 stack 規則
![](https://i.imgur.com/9J3Yd5L.png)
從報錯看 stack trace
```js
function foo() {
	throw new Error('Oops!')
}
function bar() {
	foo()
}
function baz() {
	bar()
}
baz();
```