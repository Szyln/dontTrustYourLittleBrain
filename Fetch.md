# Fetch
- 利用 fetch 可以使用 JS 來連接別人的 [[API]]
- 是一種 [[Promise]]


## 可以直接使用的 API
用 [JokeAPI](https://sv443.net/jokeapi/v2/#info) 做示範
### [[async, await, try, catch]] 來寫
單純取得之後他不會是一個 json 檔
```js
async function getJoke() {
	// 取得 endpoint
	let data = await fetch("https://v2.jokeapi.dev/joke/Any");
	console.log(data);
}

getJoke();		// 這不會是一個 json
```

> ### [[Promise]] 來寫
> fetch 也是一種 [[Promise]] 所以也可以串 then, catch
> ```js
> function getJoke() {
> 	// 取得 endpoint
> 	fetch("https://v2.jokeapi.dev/joke/Any")
> 		.then((d) => {
> 			console.log(d);
> 		}).catch((e) => {
> 			console.log(e);
> 		});
> }
> 
> getJoke();
> ```

### 調整格式
```js
async function getJoke() {
	// 取得 endpoint
	let data = await fetch("https://v2.jokeapi.dev/joke/Any");
	let parsedData = await data.json();
	console.log(parsedData);
}

getJoke();
```

## 需要有 Authorization Key 才能使用的 API
[OpenWeather](https://openweathermap.org/)
- 需要註冊，才會獲得金鑰

```js
let key = 'weathor給你的金鑰'
```
#js #async #api #promise