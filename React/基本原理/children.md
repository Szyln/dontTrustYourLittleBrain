### children
- 等同於內文 (textContent)
- 可以獨立出來當做 `React.createElement()` 的第三個（或更多）參數
- 可以多個 children

> 但是多個標籤不行，參照：[[同時生成多個標籤]]

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