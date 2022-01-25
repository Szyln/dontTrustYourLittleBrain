# React.createElement()：生成標籤
>[[ReactDOM：渲染]]

>生成標籤的原理，但實際撰寫時會用更方便的方法：[[JSX]]

```js
// 生成標籤，並指定屬性（第二個參數，為物件）
const element = React.createElement('div', {
	className: 'container',
	children: 'Hello World',		// children 等同 textContent
})

// 渲染
```
>### 原生 JS 作法
>```js
>// 生成標籤
>const element = document.createElement('div')
>// 指定屬性：內文、class 
>element.textContent = 'Hello World'
>element.className = 'container'
>
>// 渲染
>```

### children
- 等同於內文
- 可以獨立出來當做 `React.createElement()` 的第三個（或更多）參數
- 可以多個 children

> 但是多個標籤不行，要使用[[React.Fragment]]

```js
const element = React.createElement('div', {
	className: 'container',
	//  array
	children: ['Hello World', 'Goodbye World'],
})
```
```js
const element = React.createElement(
	'div', 
	{	className: 'container' },
	'Hello World', 'Goodbye World', 	// 可以多個
)
```
#react #dom #html #js