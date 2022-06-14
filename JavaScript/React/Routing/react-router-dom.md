---
title: "react-router-dom"
tag: 
- js/react 
- js/module/npm
- routing 
---
# react-router-dom
>[React Router 官網](https://reactrouterdotcom.fly.dev/)

```shell
npm install react-router-dom
```

- Routing
- Link (可以想成符合 [SPA](SPA.md) 的渲染規則的 `a` 標籤)
- 可以在 React 操作 Routing

>[[react-router-dom 版本差異]]

---
- [BrowserRouter：URL 將 React 專案連接上瀏覽器的網址](BrowserRouter：URL%20將%20React%20專案連接上瀏覽器的網址.md)
- [Routes & Route：更改 Route 時更新頁面區塊](Routes%20&%20Route：更改%20Route%20時更新頁面區塊.md)
	- [Nested Routes](Nested%20Routes.md)
- [Link：指定連結的路徑](Link：指定連結的路徑.md)
- [Navigate：將 Route Redirect 到其他頁面](Navigate：將%20Route%20Redirect%20到其他頁面.md)
- [useParams：從網址取得參數](useParams：從網址取得參數.md)

## NavLink
`Link`再多兩個功能
可以做得像分頁標籤（可以顯示目前在哪個分頁標籤上）
```jsx
function CourseID() {
	// 從 Route 取得，網址輸入：courses/${任意字串}，這裡就會取得這個 ${任意字串}
	const { courseID } = useParams()
	return (
		<div>
			{/* 取得後就可以當作一個變數用在網站上了 */}
			<h1>從 URL 取得參數為：{ courseID }</h1>
		</div>
	)
}
```
