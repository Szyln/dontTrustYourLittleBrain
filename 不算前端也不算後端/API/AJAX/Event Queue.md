---
title: "Event Queue"
aliases: <Task Queue>, <事件佇列>, <事件儲列>
tag: 
- 
---
## Event Queue
![](JavaScript%20介紹.md#^56dbb9)
![](https://i.imgur.com/4f2ZZw9.png)

想要跳脫出原本的 [Call Stack 呼叫堆疊](Call%20Stack%20呼叫堆疊.md) 規則（先進後出）的話，就會用到瀏覽器的 [thread](thread.md)：WebAPI

> WebAPI 並不是由 JavaScript 執行，JavaScript 只能呼叫他


WebAPI 處理完的指令，會丟到 Event Queue，等待 JS 把 stack 中的同步語言執行完後，才會進到 stack 中

### 非同步的語言
但 JS 無法執行非同步的語言，他們屬於 WebAPI，由瀏覽器執行

- 計時器
- `addEventListener`
- [AJAX](AJAX.md)
- [Promise](Promise.md)

```js
console.log("a");
function run() {
	console.log("b");
}
setTimeOut(run, 0);		// 產生一個 Queue 等 0 秒執行 run()
console.log("c");

// log 的順序為
// a -> c -> b
```

#js #event #ajax #async #callstack