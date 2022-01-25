# React.Fragment
>[[React.createElement()：生成標籤]]：生成內文可以多個，但生成多個標籤要使用這個功能


```jsx
const element = (
	<>
		<span>Hello</span> <span>World</span>
	</>
)

ReactDOM.render(element, document.getElementById('root'))
```
## 原始的樣子
```jsx
const element = (
	<>
		<span>Hello</span> <span>World</span>
	</>
)

ReactDOM.render(element, document.getElementById('root'))
```