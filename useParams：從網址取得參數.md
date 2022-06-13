---
title: "useParams：從網址取得參數"
tag: 
- js/react/hook
- js/module/npm
- routing 

---

##  useParams：從網址取得參數
> 後端的寫法像這樣：[Routing for pattern 回應有規律的網址](Routing%20for%20pattern%20回應有規律的網址.md)

```jsx
<Route path="/courses" element={<Courses />}>
	<Route path=":courseID" element={<CourseID />} />
</Route>
```
### 在元件中使用網址參數

```jsx
import { useParams } from 'react-route-dom'

function Courses() {
	// 如果想要指定網址參數
	const courseList = ['React', 'Angular', 'Vue']
	return (
		<div>
		{courseList.map((course) => (
			<Link to={`/courses/${course}`}>${course}</Link>
		))}
		</div>
	)
}

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