## Arguments
傳入函式中的參數，預設 `undefined`（與 [Hoisting](Hoisting.md) 有關）

```js
// 定義的時候叫 parameter
function fn1(parameters) {
	console.log(parameters)	
}
fn1(); // log undefined
// 導入的時候叫 argument
fn1(argument)
```

- [更改參數預設](更改參數預設.md)
- [Arguments 也是 Function 的屬性](Arguments%20也是%20Function%20的屬性.md)
