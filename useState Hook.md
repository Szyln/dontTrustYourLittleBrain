# useState Hook
使用 useState [[Hook]]，來控制元件的 [[State]]，並且用 [[Event Handlers]] 來規劃如何觸發

```jsx
import React, { useState } from 'react'
```

```jsx
function Greeting() {
	// destructing assignment
  const [name, setName] = React.useState('')
  const handleChange = event => setName(event.target.value)
  return (
    <div>
      <form>
				{/* for 要寫 htmlFor 避免與 js 的 for 衝突 */}
        <label htmlFor="name">Name: </label>
        <input onChange={handleChange} id="name" />
      </form>
      {name ? <strong>Hello {name}</strong> : 'Please type your name'}
    </div>
  )
}

ReactDOM.render(<Greeting />, document.querySelector('#root'))
```
>```jsx
>for 要寫 htmlFor 避免與 js 的 for 衝突
><label htmlFor="name">Name: </label>
>```
## 對應說明
>[[Destructing Assignment]]]
```jsx
// React.useState('') 記錄的是一個 array 儲存狀態
// () 內的參數是原始狀態，可以是 boolean, string, array, object 皆可
// [] 內第一個變數對應顯示在網頁上的位置
// 第二個是對應拿來更新 name state 的函式，慣用都是 set + 第一個參數名
const [name, setName] = React.useState('')
// 這個函式的參數放入要更新成的內容
// 這個函式會自動 re-render 該元件，且不影響其他頁面上元素
const handleChange = event => setName(event.target.value)
```
## Lazy Initializer
使用 [[useEffect Hook]] 的例子
```jsx
function Greeting() {
	// useState 每次更新都會執行
	// 但 React.useState() 的參數有設定的話，每次執行都要檢查一次並不實際
	// React 有提供 lazy Initializer 會自動判別需不需要執行
	// 放到一個函式內即可
  const [name, setName] = React.useState(
		// [[Logic OR]]
		() => { window.localStorage.getItem('name') || '' },
  )
}
```
```jsx
function Greeting() {
	// useState 每次更新都會執行，但 React.useState() 的參數有設定的話
	// 每次執行都要檢查一次並不實際
  const [name, setName] = React.useState(
    window.localStorage.getItem('name') || '',
  )
}
```


#react #js #hook