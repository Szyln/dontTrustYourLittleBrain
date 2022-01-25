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
 
// 渲染
```
>與[[JSX 內的 HTML 加入 JS 程式碼]]不同，單純只有儲存 string 的變數，命名用小寫開頭即可，但儲存 HTML(JSX) 的內容必須用大寫開頭（這段可能會再修改）
>```js
>// 如果沒有寫大寫，第一參數（HTML 標籤）編譯會無法正常辨識
>const element = React.createElement('message', null, 'Hello World')
>// 有大寫的話，就會辨識為一個功能
>const element = React.createElement(Message, null, 'Hello World')
>console.log(type)
>```
[[React.createElement()：生成標籤]]