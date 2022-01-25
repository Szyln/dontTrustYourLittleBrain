# Component
```jsx
function Message({children}) {
	return <div className="message">{children}</div>
}

const element = (
	<div className="container">
		<Message>Hello World</Message>
		<Message>Goodbye World</Message>
	</div>
)

// 渲染
```

```jsx
// 單純顯示字串
const message = <div>Hello World</div>
// 可以透過 function 參數來設定字串內容
const messageEdit = (props) => <div>{props.msg}</div>

const element = (
	<div>
		{message}
		{messageEdit({ msg: Hello Taiwan. })} 
	</div>
)

// 渲染
```