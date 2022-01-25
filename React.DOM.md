# React.DOM
```html
<body>
	<div id="root">
		<!-- 使用 React.DOM 將內容渲染於頁面 -->
	</div>
</body>
```
```js
// 如果是原生 JS + DOM 的話
// 取得欲渲染到的 HTML 標籤(#root)
const rootElement = document.getElementById('root')

// 生成 div 標籤
const element = document.createElement('div')
// 指定這 div 的內文及 class 
element.textContent = 'Hello World'
element.className = 'container'

// 將這個 div append
rootElement.appendChild(element)
```