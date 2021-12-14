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
	}
}

function getMovies(age, callback) {
	if(age < 12) {
		setTimeOut(() => {
			callback('cartoon');
		}, 1500);
	} else {
		setTimeout(() => {
			callback('teen movies');
		}, 1500);
	}
}

console.log('start');

// 串越多個資料就要不停的 nest 下去
// callback hell
let data = getData('Wilson', (obj) => {
	getMovies(obj.age, (str) => {
		console.log(str);
	})
});
console.log(data);

console.log('end');
```


#js #ajax #async #promise 