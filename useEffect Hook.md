# useEffect Hook
處理 [[side-effect]] 的 [[Hook]]
```jsx
const App = () => {
	// useState: name, setName	
	// setName 功能
	// useEffect
	
	return <渲染的內容 />
}
```
## 以儲存資料到 [[Local Storage]] 為例
### 先完成 useState 設定
>參照： [[useState Hook]]，設定了 `[name, setName]`

### name 存入 LocalStorage
1. 當 `name` 透過 `useState` 更新（自動 re-render 這個 app）
2. 觸發 `useEffect` 更新 [[Local Storage]]（單向更新）

>#### 選用、效能考量
>3. [[Dependency array]]：

### 檢查 LocalStorage 內有沒有既有資料
>參照 [[Lazy Initializer]]（[[useState Hook]]）
