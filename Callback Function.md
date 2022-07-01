##  Callback Function
函式當參數
```js
function greeting(name) {
	alert(`Hi, ${name}`)
}
function actionToSomebody(actionCB) {
	let name = prompt('請輸入你的名字')
	return actionCB(name)
}

actionToSomebody(greeting);
```

>- [Inline Function Expression](Inline%20Function%20Expression.md)
>- [callback function：參數裡的 function 沒有在物件裡面](callback%20function：參數裡的%20function%20沒有在物件裡面.md)
>- [Higher Order Function](Higher%20Order%20Function.md)

