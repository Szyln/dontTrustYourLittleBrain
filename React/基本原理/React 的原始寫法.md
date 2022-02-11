# React 的原始寫法
 
## 基本架構
>[[React 使用的模組]]
```js
// 匯入 React, ReactDOM: [[React 使用的模組]]

// (在 [[JSX]] 當中會提到如何簡化這段)
function App() {
	return <一些東西>;
}

// 渲染到畫面上的位置
// #root 對應 index.html body 內的 div#root
ReactDom.render(App(), document.querySelector('#root'));
```

## 多行 html
實際上會透過 [[JSX]] 來簡化寫法，不會直接這樣寫，但稍微認識一下他的原理
（從 [[單行 html 的 React 寫法]]	再改良）
>[[匯入模組]] ES6 的寫法
```js
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

// 簡化成直接執行 App()就好了
ReactDOM.render(App(), document.querySelector('#root'));
```
