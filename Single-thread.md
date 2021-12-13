# Single-thread
[[JavaScript]] 屬於 [[Single-thread]] 語言，一次只能處理一件事
```js
// sync(Synchronous) code 同步
console.log('a');
console.log('b');

// log a
// log b
```

## Event Queue
可利用 [[Event Queue]] 可以製造時間差

## Async code
用 Web API 達成，JS 本身做不到，是由網頁瀏覽器來實現
- setTimeout()
- addEventListener

## Callback Hell
```js
function getData(name) {
	setTimeout(() => {
		return {
			name,
			age: Math.floor() * 20,
			major: "CS"
		};
	}, 2000);
}
console.log('start');

// 執行的時候 let 還得不到結果，log undefined
let data = getData('Wilson');
console.log(data);

console.log('end');
```

```js
function getData(name, callback) {
	setTimeout(() => {
	// 改成 callback
		callback( {
			name,
			age: Math.floor()) * 20,
			major: "CS"
		});
	}, 2000);
}
console.log('start');

// 改成奇妙的
let data = getData('Wilson', (obj) => {
	console.log(obj);
});
console.log(data);

console.log('end');
```