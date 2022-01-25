# JSX 生成標籤

[[React.createElement()：生成標籤]]寫起來並沒有效率，透過 [[JSX]] 格式來寫可以更接近 HTML 

```js
const element = React.createElement(
	'div',
	{ className: 'Container' },
	'Hello World'
)
```
```jsx
const element = <div className="container">Hello World</div>
```
> [[ReactDOM：渲染]]
>[[JSX 內的 HTML 加入 JS 程式碼]]


#react #html #js