# React.Fragment
>[[React.createElement()：生成標籤]]：生成內文可以多個，但生成多個標籤要使用這個功能


```jsx
const element = (
	{/* 沒有內容的空標籤原本的內容是：React.Fragment，太常用了所以簡寫 */}
	<>
		<span>Hello</span>
		<span>World</span>
	</>
)

ReactDOM.render(element, document.querySelector('#root'))
```
> 沒有簡寫的 JSX 長這樣
>```jsx
>const element = (
>	<React.Fragment>
>		<span>Hello</span>
>		<span>World</span>
>	<React.Fragment/>
>)
>```

## 原始的樣子
```jsx
const helloElement = React.createElement('span', null, 'Hello')
const worldElement = React.createElement('span', null, 'World')

// 使用 React.Fragment 來產出帶有複數標籤的元素
const element = React.createElement(
	React.Fragment,
	null,
	// 第三參數就可以放入複數個標籤了，也可以放入單純的 children
	helloElement,
	' ', 
	worldElement
)

// 第一參數是不能直接 render helloElement, worldElement 的
ReactDOM.render(element, document.querySelector('#root'))
```

#react #html #js
