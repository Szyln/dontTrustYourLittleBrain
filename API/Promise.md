  # Promise
- 解決早期的 [[Callback Hell]] 現象
- 是一個 [[object]]，要用 [[Constructor]] function (`new`)來生成，生成的 object 要放入一個 function
- 分為兩個結果，resolve, reject，前者回傳資訊（`then`），後者回傳錯誤資訊（`catch`）

## 兩個結果
### resolve
```js
// constructor
let example = new Promise((resolve, reject) => {
	resolve({一個 object});

})

example.than((d) => {
	console.log(d);
})
```
### reject
```js
let example = new Promise((resolve, reject) => {
	reject(new Error('not allowed')); 
});

example.catch((e) => {
	console.log(e);
})
```

## 改寫 [[Callback Hell]]
```js

function getData(name) {
	if (name == "Wilson") {
		return new Promise((resolve, reject) => {
			resolve({ 
				name: "Wilson",
				age: Math.floor(Math.radom() * 20)
			})
		})
	} else {
		return new Promise((resolve, reject) => {
			reject(new Error("Not allowed to access data"))
		})
	}
}

function getMovies(age) {
	if(age < 12) {
		return new Promise((resolve, reject) => {
			resolve({ text: 'cartoon' });
	} else if(age < 18) {
		return new Promise((resolve, reject) => {
			resolve( {text: "teen movies" });
		})
	} else {
		return new Promise((resolve, reject) => {
			reject( new Error("not exist."));
		})
	}
}

getData('Wilson')
	// 第一個 then 是 getData 的結果
	// 記得要 return 才能給第二個 then 使用
	.then((obj) => {
		return getMovies(obj.age);
	// 第二個 then 是 getMovies 的結果
	}).then((message) => {
		console.log(message.text);
	// 可能是第一個也可能是第二個，看 reject 在什麼時候發生
	}).catch(e => {
		console.log(e);
	});

```
> 也可以使用 [[4.箭頭函式 arrow function]]
> ```js
> getData('Wilson')
> 	.then((obj) => getMovies(obj.age))
> 	.then((message) => { console.log( message.text )};
> 	).catch(blablabla);
> ```

[[async, await, try, catch]]
#js #ajax #async #promise