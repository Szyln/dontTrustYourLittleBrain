---
title: "Single-thread"
tag: 
- 
---
# Single-thread
![](JavaScript%20介紹.md#^56dbb9)

>- [JavaScript](JavaScript.md) 通常是在瀏覽器中運作的，瀏覽器還有其他的 [thread](thread.md)（webapis）可以用
>- 看看 [JavaScript](JavaScript.md) 如何與 webapis 配合：[Call Stack 呼叫堆疊](Call%20Stack%20呼叫堆疊.md)

```js
// sync(Synchronous) code 同步
console.log('a');
console.log('b');

// log a
// log b
```

- 可利用 [[Event Queue]] 可以製造時間差

## Async code
用 Web API 達成，JS 本身做不到，是由網頁瀏覽器來實現
- setTimeout()
- addEventListener

## [[Promise]]
#js #event #ajax #async #promise 