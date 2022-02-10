### 單行 html 的 React 寫法
最原始是這樣寫
```js
function App() {
// 參數：標籤、css、內容
	return React.createElement('h1', null, 'ths is react app');
}

ReactDOM.render(React.createElement(App), document.querySelector('#root'));
```