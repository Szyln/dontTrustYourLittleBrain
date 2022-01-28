# 用元件處理 CSS Styling
```jsx
function Box({style, size, className = '', ...rest}) {
  const sizeClassName = size ? `box--${size}` : ''
  return (
    <div
      className={`box ${className} ${sizeClassName}`}
      style={{fontStyle: 'italic', ...style}}
      {...rest}
    />
  )
}

const element = (
  <div>
    <Box size="small" style={{backgroundColor: 'lightblue'}}>
      small lightblue box
    </Box>
    <Box size="medium" style={{backgroundColor: 'pink'}}>
      medium pink box
    </Box>
    <Box size="large" style={{backgroundColor: 'orange'}}>
      large orange box
    </Box>
    <Box>sizeless box</Box>
  </div>
)
```

---
## 原則
>[[Component：可重複利用、自定參數的元件]]
>[[Styling in JSX]]

- 會多次出現的類似內容，就可以做成元件
- 內容若有需要微調的需求，則設定參數供調整

### 以 className 為例
1. 找出類似內容
```jsx
const element = (
	<div>
		{/* 觀察有沒有可以異中求同的要素： className 有 box */}
		<div className="box box-small">small box</div>		
		<div className="box box-medium">medium box</div>
	</div>
)
```
2. 拉出來做成元件
```jsx
// 建立 Box 元件
function Box(props) {
	return (
		{/* 最一開始長這樣，沒有異中求同，只有單純元件化 */}
		<div {...props} />
	)
}
// 改寫
const element = (
	<div>
		{/* 全部屬性都手動寫 */}
		<Box className="box box-small">small box</Box>		
		<Box className="box box-medium">medium box</Box>
	</div>
)
```
3. 不同的內容則拉出來做自訂參數
```jsx
function Box({className, ...rest}) {
	return (
		// 注意包在 HTML 標籤內要寫 JS 程式碼的話要用 {} 包起來
		<div className={`box ${className}`} {...rest} />
	)
}
const element = (
	<div>
		{/*  */}
		
		<Box className="box-small">small box</Box>		
		<Box className="box-medium">medium box</Box>
	</div>
)
```
>## 注意
>不要這樣寫，如果手動寫 `props` 的時候寫了 `className` 屬性會蓋過前者（只能有一個 `className`）
>```jsx
><div className="box" {...props} />
>```

```jsx
const element = (
	<div>
		{/*  */}
		<Box className="box-small">small box</Box>		
		<Box className="box-medium">medium box</Box>
	</div>
)
```
```jsx
const element = (
	<div>
		{/* 兩個標籤類似，可以將 */}
		<Box className="box box-small">small box</Box>		
		<Box className="box box-medium">medium box</Box>
	</div>
)

// 渲染 element
```