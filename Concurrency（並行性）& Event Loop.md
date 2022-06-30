---
title: "Concurrency（並行性）& Event Loop"
tag: 
- 
---

##  Concurrency（並行性）& Event Loop
>[看動態版](http://latentflip.com/loupe/?code=Y29uc29sZS5sb2coJ2hpJykKCnNldFRpbWVvdXQoZnVuY3Rpb24gY2IoKSB7Cgljb25zb2xlLmxvZygndGhlcmUnKQp9LCA1MDAwKQoKY29uc29sZS5sb2coJ2J5ZScp!!!PGJ1dHRvbj5DbGljayBtZSE8L2J1dHRvbj4%3D)


![](JavaScript%20介紹.md#^56dbb9)

![](https://i.imgur.com/4f2ZZw9.png)

- stack：JS 執行同步語言的地方，遵守 LIFO 規則，如果遇到非同步語言，會丟給瀏覽器處理，繼續處理同步語言
- WebAPI：瀏覽器的執行緒，接到 JS 的呼叫的時候，就會處理非同步語言，完成後丟進到 [Event Queue](Event%20Queue.md) 中
- [Event Queue](Event%20Queue.md)：等待 JS 將同步語言完成，完成後由 Event Loop 負責安排進 stack 中
- Event Loop：stack 清空 --> 持續監視 Event Queue --> 將 [Event Queue](Event%20Queue.md) 的第一個 Task 丟進 stack 中 --> （loop）


```js
console.log('hi')

setTimeout(function cb() {
	console.log('there')
}, 5000)

console.log('bye')
```