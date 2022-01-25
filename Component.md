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
## 
>[[JSX 生成標籤]]
```jsx
	// 單純顯示字串
const Message = <div>Hello World</div>
// 可以透過 function 參數來設定字串內容
const MessageEdit = props => <div>{props.children}</div>

const element = (
	<div>
		{/* 用 {} 視覺上不統一*/}
		{Message}
		{MessageEdit({ children: "Hello Taiwan." })}
		{/* 沒辦法直接寫 <Message /> */}
		<MessageEdit children="Hello America." />
	</div>
)
// type: 'div'
console.log(Message);
// type: MessageEdit(props)
// 為一個 function 而非標籤
console.log(<MessageEdit children="Hello America." />);

// 渲染
```
>與[[JSX 內的 HTML 加入 JS 程式碼]]不同，單純只有儲存 string 的變數，命名用小寫開頭即可，但儲存 HTML(JSX) 的內容必須用大寫開頭（這段可能會再修改）
>```js
>// 如果沒有寫大寫，第一參數（HTML 標籤）編譯會無法正常辨識
>const element = React.createElement('messageEdit', null, 'Hello World')
>// 有大寫的話，就會辨識為一個功能
>const element = React.createElement(MessageEdit, null, 'Hello World')
>```
[[React.createElement()：生成標籤]]