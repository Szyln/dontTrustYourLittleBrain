# JSX(JavaScript eXtension)
- React 的擴充功能
- 可以讓 JS 寫得像 HTML 一樣，不用像 [[React 基本原理]]一樣要一直用 `React.createElement()` 的語法
- 用 [[Babel]] 來編譯 

```js
// App() 的 A 一定要大寫
function App() {
	return (
		// function 內 return 只能執行一次，所以一定要包起來
		<div>
			<h1></h1>
			<p></p>
		</div>			
	)
}
```