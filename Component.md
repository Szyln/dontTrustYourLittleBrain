# Component
- Component 可以透過**函數** Function 做出可以自定參數的元件（這邊可能之後會再改）
- 需要重複使用的內容只需要一個函數來完成
- 透過參數可以調整每個生成出來的元件
- 要大寫開頭

>[[JSX 生成標籤#利用 重複使用]]僅限於純 HTML 的重複利用

```jsx
// 可以透過 function 參數來設定字串內容
// 解釋：使用元件時，標籤中的 children 屬性（element）會顯示於 {props.children}
// 要大寫開頭
const MessageEdit = props => <div>{props.children}</div>

const element = (
	<div>
		{/* 下列寫法效果一樣 */}
		{/* 類似 [[JSX 生成標籤#利用 重複使用]] 的寫法也可以，但元件可以用以下寫法 */}
		{MessageEdit({ children: "Hello Taiwan." })}
		{/* 元件參數若是任意屬性的話這樣寫 */}
		<MessageEdit children="Hello America." />
		{/* 是 children 的話這樣寫易讀性最好 */}
		<MessageEdit>Hello Japan.</MessageEdit>
	</div>
)

// 渲染
```
>與 [[JSX 內的 HTML 加入 JS 程式碼]]不同（命名用小寫開頭），變數儲存的內容若是函數（Component），要大寫開頭
>```js
>// ！：如果沒有寫大寫，第一參數（HTML 標籤）編譯會無法正常辨識
>const element = React.createElement('messageEdit', null, 'Hello World')
>```
>```jsx
>// 有大寫的話，就會辨識為一個函數
>const element = React.createElement(MessageEdit, null, 'Hello World')
>
>// type: MessageEdit(props)
>// 為一個 function 而非標籤
>console.log(<MessageEdit children="Hello America." />);
>```
[[React.createElement()：生成標籤]]


#react #html #js #component #function 