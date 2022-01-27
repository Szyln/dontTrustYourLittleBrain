## JSX HTML 內使用變數
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