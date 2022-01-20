# React 基本原理
```js
import React from 'react';
import ReactDOM from'react-dom';


function App() {
	// 參數：標籤、css、內容
	// 一個 function 只能 return 一次，多行內容要用 array 
	return React.createElement('div', null, [
		React.creatElement('h1', null, 'title'),
		React.creatElement('h2', null, 'subtitle'),
		React.creatElement('h3', null, )
	]);
}

  

// root 對應 index.html body 內的 div#root
// 決定 react 要 render 到哪
ReactDOM.render(App(), document.querySelector('#root'));
```
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