## Lazy Initializer
使用 [[useEffect Hook]] 的例子
```jsx
function Greeting() {
	// useState 每次更新都會執行
	// 但 React.useState() 的參數有設定的話，每次執行都要檢查一次並不實際
	// React 有提供 lazy Initializer 會自動判別需不需要執行
	// 放到一個函式內即可
  const [name, setName] = React.useState(
		// [[Logic OR]]
		() => { window.localStorage.getItem('name') || '' },
  )
}
```
```jsx
function Greeting() {
	// useState 每次更新都會執行，但 React.useState() 的參數有設定的話
	// 每次執行都要檢查一次並不實際
  const [name, setName] = React.useState(
    window.localStorage.getItem('name') || '',
  )
}
```