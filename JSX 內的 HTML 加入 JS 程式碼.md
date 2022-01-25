# JSX 內的 HTML 加入 JS 程式碼
在 [[JSX]] 裡 return 的 HTML 內想加入 JS 程式碼的話需要使用 `{}`

## 使用變數
```jsx
const children = 'Hello'
const className = 'container'
const element = <div className={className}>{children}</div>
```
>[[定義屬性(props)]]


```jsx
const App = () => {
	let people = ['Mike', 'Ken', 'Sam']
	return (
	<div>
		{/* 加入{} 就可以寫 JS 了*/}
		<h1>{ 3 * 2 }</h1>
		<p>My name is { name[1] }</p>
	</div>
	)
};
```
## 迴圈
```jsx
const App = () => {
	let people = ['Mike', 'Ken', 'Sam']
	return (
	<div>
		<p>List of team member:</p>
		{/* 箭頭函式可以簡化 */}
		{/*
			people.map(person => {
				reutrn <p>{name}</p>
			})
		*/)}
		{/* 使用迴圈要記得，return 的 HTML 再包一次 {} */}
		{
			people.map(person => (<p>{name}</p>)
		}
	</div>
	)
};
```
>[[陣列的循環 for, forEach, map]]
>[[4.箭頭函式 arrow function]]