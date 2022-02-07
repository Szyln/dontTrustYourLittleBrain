# Component
- 元件大致上就是用 function 來 return HTML 元素，其中可以自訂參數來調整元素，方便重複使用
- 除了用 function 之外也有用 [[Class]] 來寫的版本：[[Class Component]]
- 早期主要是用 [[Class Component]]，現在多建議 function component 搭配 [[Hook]] 來寫（16.8 版）
- 透過 [[定義屬性(props)]]（參數）可以調整每個生成出來的元件
- 要大寫開頭
- 一個元件可以在另一個元件裡（詳細要進一步了解渲染的機制： [[Hook]]）
- [[元件匯出]]

>單純使用 `{}`  可以重複利用存到變數內的 html：[[JSX 生成標籤#HTML 透過存到變數內來重複使用]]
>但要可以調整參數就要學會元件的概念

---

```jsx
// 元件的參數可以指定很多屬性，例如 children, style, 或是自訂等
// 用 props.屬性 來讀取
const MessageEdit = props => <div>{props.children}</div>
```
```jsx
const element = (
  <div>
    {/* 下列寫法效果一樣 */}
    {/* 類似 [[JSX 生成標籤#HTML 透過存到變數內來重複使用]] 的寫法也可以，但元件可以用以下寫法 */}
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