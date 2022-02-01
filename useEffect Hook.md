# useEffect Hook
處理 [[side-effect]] 的 [[Hook]]

## 以儲存資料到 [[Local Storage]] 為例
### 先完成 useState 設定
>參照： [[useState Hook]]，設定了 `[name, setName]`

### name 存入 LocalStorage
1. 當 `name` 透過 `useState` 更新（自動 re-render 這個 app）
2. 觸發 `useEffect` 更新 [[Local Storage]]（單向更新）

>3. （選用、效能考量）Dependency array：設定如果 [[Local Storage]] 沒有被更動的話，就不用執行 `useEffect`

```jsx
// name 更新 -> 更新 localStorage（注意：這是單向更新）
React.useEffect(() => {
  console.log('useEffect 被執行囉');
  window.localStorage.setItem('name', name)
  // Dependency array：讓 useEffect 可以雙向更新的參數
	// 若如果沒有更新就不執行這個 useEffect
	// 
}, [name])
```

### 檢查 LocalStorage 內有沒有既有資料
>[[useState Hook]]
>[[Lazy Initializer]]

```jsx
const [name, setName] = React.useState(
	// [[Logic OR]]
	// 取得 localStorage 是否有這個值，否則預設值為空字串
	window.localStorage.getItem('name') || '',
)
```
### 
```jsx
  // useEffect：每次 greeting 執行，就 name 存進 localStorage
  React.useEffect(() => {
    window.localStorage.setItem('name', name)
  })




```
> [[Logic OR]]