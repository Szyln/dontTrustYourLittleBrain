---
title: "Call Stack（呼叫堆疊）"
tag: 
- js/executionContext
---
## Call stack（呼叫堆疊）
> - [loupe：直接看 Call Stack 運作的樣子](http://latentflip.com/loupe/?code=ZnVuY3Rpb24gZjEoKSB7CiAgY29uc29sZS5sb2coJ1RoaXMgaXMgZjEnKQoKICBmMigpCgogIGZ1bmN0aW9uIGYyKCkgewogICAgY29uc29sZS5sb2coJ1RoaXMgaXMgZjInKQoKICAgIGYzKCkKCiAgICBmdW5jdGlvbiBmMygpIHsKICAgICAgY29uc29sZS5sb2coJ1RoaXMgaXMgZjMnKQoKICAgICAgY29uc29sZS5sb2coJ2YzIGRvbmUnKQogICAgfQoKICAgIGNvbnNvbGUubG9nKCdmMiBkb25lJykKICB9CgogIGNvbnNvbGUubG9nKCdmMSBkb25lJykKfQoKZjEoKQ%3D%3D!!!PGJ1dHRvbj5DbGljayBtZSE8L2J1dHRvbj4%3D)
> - [What the heck is the event loop? | Philip Roberts | JSConf EU](https://www.youtube.com/watch?v=8aGhZQkoFbQ&t=107s)


Call Stack 的運作模式一個像收納箱，先放進去（被呼叫的 function）的東西會最後才拿出來（執行）（LIFO，Last-In-First-Out 後進先出）

JavaScript 是單一線性(single-[[thread]])程式語言，一次只能做一件事，[[執行環境 Execution Context]]（的 [[Execution Phase]] 階段） 就是按照這個 Call Stack 的結構在跑程式碼的。

```
one thread == one call stack == one thing at a time
```


>- Call：指 Calling functions ，呼 function 時就會產生 call stack（看下面例子）
>- Stack：一種資料結構（資料結構跟演算法相關）

---

- [call stack 範例](call%20stack%20範例.md)
- [Devtool 報錯看 stack 規則](Devtool%20報錯看%20stack%20規則.md)
- [Blowing the stack（堆疊爆炸）](Blowing%20the%20stack（堆疊爆炸）.md) 

[Concurrency（並行性）& Event Loop](Concurrency（並行性）&%20Event%20Loop.md)

![](https://i.imgur.com/4f2ZZw9.png)
