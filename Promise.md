# Promise
解決早期的 [[Callback Hell]] 現象
```js
let example = new Promise((resolve, reject) => {
	resolve({一個 object});
	reject(new Error('not allowed')); 
})

example.than((d) => {
	console.log(d);
}).catch((e) => {
	console.log(e)
})
```

#js #event #ajax #async #promise 