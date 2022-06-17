---
title: "React 中使用 API 串接第三方服務（未完成）"
tag: 
- js/react/api
- progress
---

##  React 中使用 API 串接第三方服務（未完成）
[如何在 React 中使用 Axios](https://chinese.freecodecamp.org/news/how-to-use-axios-with-react/)

不要忘記串第三方就是一種 [side-effect](side-effect.md) ，要用 [useEffect Hook](useEffect%20Hook.md)

### 未讀
- [How to Get Started With React + JSON Server](https://www.webtips.dev/react-json-server) 難 useContent
- [useEffect – How to test React Effect Hooks](https://cultivate.software/useeffect/#how-to-test)
- [Wait for API call data before render react hooks](https://stackoverflow.com/questions/58956828/wait-for-api-call-data-before-render-react-hooks)
- [React.useEffect Hook – Common Problems and How to Fix Them](https://www.freecodecamp.org/news/most-common-react-useeffect-problems-and-how-to-fix-them/)

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
