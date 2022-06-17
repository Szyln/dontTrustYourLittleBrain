---
title: "React 中使用 API 串接第三方服務"
tag: 
- #js/react/api
---

##  React 中使用 API 串接第三方服務
[如何在 React 中使用 Axios](https://chinese.freecodecamp.org/news/how-to-use-axios-with-react/)

不要忘記串第三方就是一種 [side-effect](side-effect.md) ，要用 [useEffect Hook](useEffect%20Hook.md)

### 正確示範
```jsx
// useEffect 用下去
const [data, setData] = useState([])
useEffect(() => {
	axios.get(url).then((res) => {
		setData(res.data)
	})
})
```
### 錯誤示範
```jsx
// 這種寫法會得到資料還在 pending 的結果
const data = axios.get(url).then((res) => (res.data))
// 透過非同步會得到 react 不允許的結果
const data = await axios.get(url).then((res) => (res.data))
```
