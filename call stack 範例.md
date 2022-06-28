## call stack 範例
### 第一個
>[看動態版](http://latentflip.com/loupe/?code=ZnVuY3Rpb24gZm4xKGEsIGIpIHsgCglyZXR1cm4gYSAqIGI7Cn0KZnVuY3Rpb24gZm4yKGMpIHsJCglyZXR1cm4gZm4xKGMsIGMpOwp9CmZ1bmN0aW9uIGZuMyhkKSB7CglyZXR1cm4gZm4yKGQpCn0KCmNvbnNvbGUubG9nKGZuMygxMCkp!!!PGJ1dHRvbj5DbGljayBtZSE8L2J1dHRvbj4%3D)
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
### 第二個
>[看動態版](http://latentflip.com/loupe/?code=ZnVuY3Rpb24gZjEoKSB7Cgljb25zb2xlLmxvZygiZjEiKTsKCQoJZjIoKQoKCWZ1bmN0aW9uIGYyKCkgewoJCWNvbnNvbGUubG9nKCJmMiIpOwkKCQlmMygpOwkJCQoJCQoJCWZ1bmN0aW9uIGYzKCkgewkJCQoJCQljb25zb2xlLmxvZygiZjMiKTsKCQl9CQkJCQkKCX0JCQkJCQkKCQkJCQkJCQkKCWNvbnNvbGUubG9nKCJkb25lIik7CQp9CQkJCQkJCgpmMSgp!!!PGJ1dHRvbj5DbGljayBtZSE8L2J1dHRvbj4%3D)
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

宣告 function 有 [Hoisting](Hoisting.md) 效果，進出 stack 的順序為
```
f1() --> log('f1') --> // f1 進去 stack，log 直接執行
f2() --> log('f2') --> // 同上
f3() --> log('f3') --> // 同上
log('done')	-->

將 stack 中的 f3 --> f2 --> f1 依 LIFO 執行
```