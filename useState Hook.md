# useState Hook
>[[Event Handlers]]
>[[State]]
>[[Hook]]

使用 useState [[Hook]]，來控制元件的 [[State]]，並且用 [[Event Handlers]] 來規劃如何觸發
```jsx
function Greeting() {
	// destructing assignment
  const [name, setName] = React.useState('')
  const handleChange = event => setName(event.target.value)
  return (
    <div>
      <form>
        <label htmlFor="name">Name: </label>
        <input onChange={handleChange} id="name" />
      </form>
      {name ? <strong>Hello {name}</strong> : 'Please type your name'}
    </div>
  )
}

ReactDOM.render(<Greeting />, document.querySelector('#root'))
```

## 對應說明
>[[Destructing Assignment]]]
```jsx
// React.useState('') 記錄的是一個 array 儲存狀態
// () 內的參數是原始狀態
// [] 內第一個變數對應顯示在網頁上的位置，第二個是對應拿來更新 name state 的函式
const [name, setName] = React.useState('')
// 這個函式會自動 re-render 該元件，且不影響其他頁面上元素
const handleChange = event => setName(event.target.value)
```

#react #js #hook