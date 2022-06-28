---
title: "Concurrency（並行性）& Event Loop"
tag: 
- 
---

##  Concurrency（並行性）& Event Loop
>[看動態版](http://latentflip.com/loupe/?code=Y29uc29sZS5sb2coJ2hpJykKCnNldFRpbWVvdXQoZnVuY3Rpb24gY2IoKSB7Cgljb25zb2xlLmxvZygndGhlcmUnKQp9LCA1MDAwKQoKY29uc29sZS5sb2coJ2J5ZScp!!!PGJ1dHRvbj5DbGljayBtZSE8L2J1dHRvbj4%3D)

- JavaScript 是單執行緒語言，不能同時執行多個動作
- 瀏覽器提供 Web API （例如 `setTimeOut`）提供更多執行緒（JS 只能呼叫他們）

>- Event Loop：如果 stack 中已清空，就將任務佇列第一個 task 丟回 stack 中執行
>- task queue：任務佇列，webapis 處理的非同步指令完成後存放的地方

```js
console.log('hi')

setTimeout(function cb() {
	console.log('there')
}, 5000)

console.log('bye')
```