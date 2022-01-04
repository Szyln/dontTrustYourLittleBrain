# process(node)
[javaTpoint](https://www.javatpoint.com/nodejs-process)

一個 [[Node.js]] 的全域物件，可以檢視目前的 platform, version 等

```js
app.get('/', (req, res) => {
	console.log(process.platform);
	console.log(process.version);
	console.log(process.env);
})
```