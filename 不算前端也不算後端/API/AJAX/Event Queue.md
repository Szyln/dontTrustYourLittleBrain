---
title: "Event Queue"
aliases: <Task Queue>, <事件佇列>, <事件儲列>
tag: 
- 
---
## Event Queue


Event Queue 利用時間差做出類似可以處理很多事的效果

JS 屬於 [Single-thread](Single-thread.md) 的語言，想要跳脫出原本的 [Call Stack 呼叫堆疊](Call%20Stack%20呼叫堆疊.md) 規則（先進後出）的話，就會用到瀏覽器的 [thread](thread.md)：WebAPI

>- 屬於[Call Stack 呼叫堆疊](Call%20Stack%20呼叫堆疊.md) 的其中一個不是 [JavaScript](JavaScript.md) 來執行的階段

### 非同步的語言
但 JS 裡面也有非同步的語言，他們屬於 WebAPI
- 計時器
- Ajax
- Promise

### 
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