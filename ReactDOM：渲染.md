# ReactDOM
```js
// 可以直接簡寫成：
ReactDom.render('要渲染的內容', document.quertSelector('#渲染位置'));
// 要渲染的內容只能有一個
```

---

```html
<body>
	<div id="root">
		<!-- 使用 React.DOM 將內容渲染於頁面 -->
	</div>
</body>
```
```js
// 生成標籤：[[React.createElement()：生成標籤]]再講
const element = '等到後面再講'

// 取得渲染位置
const rootElement = document.querySelector('#root')
// 將標籤 append 到 rootElement 上
ReactDOM.render(element, rootElement)

```
```js
// 可以直接簡寫成：
ReactDom.render(element, document.quertSelector('#root'));
```
>## 原生 JS 作法
>```js
>// 生成標籤
>const element = document.createElement('div')
>
>// 取得欲渲染到的 HTML 標籤(#root)
>const rootElement = document.querySeletor('#root')
>// 將標籤 append 到 rootElement 上
>rootElement.appendChild(element)
>```

#react #dom #html #js