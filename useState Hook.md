# useState Hook
>再用 [[useEffect Hook]] 看如何搭配 [[side-effect]] 來寫更複雜的 [[Hook]]，並且改良 `useState` 的初始值設定 （[[Lazy Initializer]]）


使用 useState [[Hook]]，來控制元件的 [[State]]，並且用 [[Event Handlers]] 來規劃如何觸發

```jsx
import React, { useState } from 'react'
```

```jsx
function Greeting() {
	// destructing assignment
	// 更進階的初始值設定：[[Lazy Initializer]]
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
>關於 `[name, setName]` 原理：[[Destructing Assignment]]


```jsx
// name: 自訂名稱，setName：name 的更改 state 用函數
const [name, setName] = React. useState ('該名稱的原始狀態，任意資料類型皆可')
// setName 參數放入要更新成的內容
// setName 會自動 re-render 該元件，且不影響其他頁面上元素
const handleChange = event => setName(event.target.value)
```



#react #js #hook