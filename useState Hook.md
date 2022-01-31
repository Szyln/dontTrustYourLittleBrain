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
>[[Destructing Assignment]]


```jsx
const [該名稱, 更動該元素的函式，通常會是set開頭] = React.useState('該名稱的原始狀態，任意資料類型皆可')
// 使用set開頭的那個函式，放入要更新成的內容
// 這個函式會自動 re-render 該元件，且不影響其他頁面上元素
const handleChange = event => setName(event.target.value)
```
[[Lazy Initializer]]


#react #js #hook