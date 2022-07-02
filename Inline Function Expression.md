## Inline Function Expression
>[Callback Function](Callback%20Function.md) 的變形，不這樣寫也沒差

- 內嵌函式表達式
- function 也是物件，可以像物件一樣直接放入 argument
- function 的 callback 參數 ＆ 該 function 是在同一個作用域中，可以直接將 callback 直接在 function 參數裡面定義，==沒有差別==

>[callback function：參數裡的 function 沒有在物件裡面](callback%20function：參數裡的%20function%20沒有在物件裡面.md)

### 先定義再 callback
```js
function greeting(name) {
	alert(`Hi, ${name}`)
}

function actionTo(actionCB, name) {
	actionCB(name)
}

actionTo(greeting, 'Amy');
```
### callback 定義直接寫到參數中
```js


function actionTo(actionCB, name) {
	actionCB(name)
}

actionTo(function greeting(name) {
	alert(`Hi, ${name}`)
}, 'Amy');
```