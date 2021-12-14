# Promise
- 解決早期的 [[Callback Hell]] 現象
- 是一個 [[object]]，要用 [[Constructor]] function (`new`)來生成，生成的 object 要放入一個 function
- 分為兩個結果，resolve, reject，前者回傳資訊（`then`），後者回傳錯誤資訊（`catch`）

```js
// constructor
let example = new Promise((resolve, reject) => {
	resolve({一個 object});

})

example.than((d) => {
	console.log(d);
})
```
```js
let example = new Promise((resolve, reject) => {
	reject(new Error('not allowed')); 
});

example.catch((e) => {
	console.log(e);
})
```
> [[Mongoose Promise and Query]]

#js #event #ajax #async #promise 