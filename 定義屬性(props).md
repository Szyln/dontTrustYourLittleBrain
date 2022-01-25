# 定義屬性

- 兩種方法效果一樣
## 只用 JS 定義屬性的值 Value
>[[JSX 內的 HTML 加入 JS 程式碼]]
```jsx
const children = 'Hello'
const className = 'container'

const element = <div className={className}>{children}</div>
// 可以簡寫為
const element = <div className={className} clildren={children} />
```
## 用 JS 物件定義屬性（ [[Key-Value Pair]] ）
HTML 屬性中，重複的屬性，後者會蓋過前者
```jsx
// 使用物件儲存屬性們
const props = { children: 'Hello', className: 'container' }
const element = <div {...props} />
```

### 增加屬性（物件以外）
```jsx
// 寫在 props 前
const element = <div id="app-root" {...props} />
```
### 覆蓋屬性
```jsx
// 寫在 props 後
const element = <div {...props} className="not-container" />
```