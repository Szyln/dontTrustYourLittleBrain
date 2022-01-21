# React 基本原理
實際上不會這樣寫，但稍微認識一下他的原理

## 多行 html
（從 [[React 基本原理#單行 html]]	再改良）
>[[匯入模組]] ES6 的寫法
```js
// ES6 匯入模組的寫法
import React from 'react';
import ReactDOM from'react-dom';


function App() {
	// 參數：標籤、css、內容
	// 一個 function 只能 return 一次，多行內容要用 array 
	// css 可以寫 in-line style
	return React.createElement('div', { style: { color: 'red' } }, [
		React.creatElement('h1', null, 'title'),
		React.creatElement('h2', null, 'subtitle'),
		React.creatElement('h3', null, )
	]);
}

  

// root 對應 index.html body 內的 div#root
// 決定 react 要 render 到哪
// 簡化成直接執行 App()就好了
ReactDOM.render(App(), document.querySelector('#root'));
```
### 單行 html
最原始是這樣寫
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