# JSX 生成標籤

[[React.createElement()：生成標籤]]寫起來並沒有效率，透過 [[JSX]] 格式來寫可以更接近 HTML 

```js
const HelloElement = React.createElement(
	'h1',
	{ className: 'title' },
	'Hello World'
)
```
```jsx
const HellowElement = <h1 className="title">Hello World</h1>
```
## 利用 {} 重複使用
>[[JSX 內的 HTML 加入 JS 程式碼]]
```jsx
const element = (
	<div>
		{HelloElement}
	</div>
)
```
> [[ReactDOM：渲染]]


#react #html #js