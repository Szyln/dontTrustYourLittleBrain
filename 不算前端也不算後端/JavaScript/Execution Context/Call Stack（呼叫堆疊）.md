---
title: "Call Stack（呼叫堆疊）"
tag: 
- js/executionContext
---
## Call stack（呼叫堆疊）
> [loupe：直接看 Call Stack 運作的樣子](http://latentflip.com/loupe/?code=ZnVuY3Rpb24gZjEoKSB7CiAgY29uc29sZS5sb2coJ1RoaXMgaXMgZjEnKQoKICBmMigpCgogIGZ1bmN0aW9uIGYyKCkgewogICAgY29uc29sZS5sb2coJ1RoaXMgaXMgZjInKQoKICAgIGYzKCkKCiAgICBmdW5jdGlvbiBmMygpIHsKICAgICAgY29uc29sZS5sb2coJ1RoaXMgaXMgZjMnKQoKICAgICAgY29uc29sZS5sb2coJ2YzIGRvbmUnKQogICAgfQoKICAgIGNvbnNvbGUubG9nKCdmMiBkb25lJykKICB9CgogIGNvbnNvbGUubG9nKCdmMSBkb25lJykKfQoKZjEoKQ%3D%3D!!!PGJ1dHRvbj5DbGljayBtZSE8L2J1dHRvbj4%3D)


Call Stack 的運作模式一個像收納箱，先放進去（被呼叫的 function）的東西會最後才拿出來（執行）（LIFO，Last-In-First-Out 後進先出）

JavaScript 是單一線性(single-[[thread]])程式語言，一次只能做一件事，[[Execution Context]]（的 [[Execution Phase]] 階段） 就是按照這個 Call Stack 的結構在跑程式碼的。

```
one thread == one call stack == one thing at a time
```


>- Call：指 Calling functions ，呼 function 時就會產生 call stack（看下面例子）
>- Stack：一種資料結構（資料結構跟演算法相關）

### 範例
#### 第一個
```js
function fn1(a, b) { // 呼叫：4th / 執行： 1st
	return a * b;
}
function fn2(c) {		 // 呼叫：3rd / 執行： 2nd
	return fn1(c, c);
}
function fn3(d) {		 // 呼叫：2nd / 執行： 3rd
	return fn2(d)
}

console.log(fn3(10)) // 呼叫：1st / 執行： 4th
```
![](https://i.imgur.com/kEmgNWJ.png)
#### 第二個
宣告 function 有 [Hoisting](Hoisting.md) 效果，呼叫順序為
```
f1() --> log('f1') --> f2() --> f3()
```
```

```
```js
function f1() {
	console.log("f1");			// 1. log f1
	
	f2()

	function f2() {
		console.log("f2");		// 2. log f2
		
		f3();			
		
		function f3() {			
			console.log("f3");	// 3. log f3
		}						// 4. f3 執行完畢，清除 f3
	}							// 5. f2 執行完畢，清除 f2
								
	console.log("done");		// 6. log done 
}								// 7. f1 執行完畢，清除 f1

f1()
```