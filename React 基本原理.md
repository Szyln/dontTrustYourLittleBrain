# React 基本原理
```js
const React = require('react');
const ReactDOM = require('react-dom');


function App() {
// 參數：標籤、css、內容
	return React.createElement('h1', null, 'ths is react app');
}

  

// root 對應 index.html body 內的 div#root
// 決定 react 要 render 到哪
ReactDOM.render(React.createElement(App), document.querySelector('#root'));
```