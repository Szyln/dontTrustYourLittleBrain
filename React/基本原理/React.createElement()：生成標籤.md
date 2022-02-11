# React.createElement()：生成標籤
>[[ReactDOM：渲染]]
>[[JSX 生成標籤]]
>[[React.Fragment：生成複數標籤]]

生成標籤的原理，但實際撰寫時會用更方便的方法：[[JSX]]

```js
// 匯入 [[React 使用的模組]]

// 生成標籤，並指定屬性（第二個參數，為物件）
// 屬性參數包含：寫入 CSS、className 等等等
const element = React.createElement('div', {
  className: 'container',
  children: 'Hello World', // children 等同 textContent
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
## children
等同於 textContent
>[[children]]


#react #dom #html #js