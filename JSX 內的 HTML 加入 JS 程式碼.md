# JSX 內的 HTML 加入 JS 程式碼
在 [[JSX]] 裡 return 的 HTML 內想加入 JS 程式碼的話需要使用 `{}`

- [[JSX HTML 內使用變數]]
- [[JSX HTML 內寫迴圈]]


```jsx
function CharacterCount({text}) {
  return (
    <div>
			{/* kent */}
      {`The text "${text}" has `}
      {text.length ? <strong>{text.length}</strong> : 'No'}
      {' characters'}
			{/* 我*/}
      {`The text "${text}" has `}
      {text.length ? <strong>{text.length}</strong> : 'No'}
      {' characters'}
    </div>
  )
}
``` 