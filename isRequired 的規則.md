### isRequired 的規則
```jsx
componentName.propTypes = {
	propA: PropTypes.string.isRequired,
}
```
`isRequired` 可以定義該 prop 必填，漏填的時候就會跳紅色警示
如果沒有寫 `isRequired` 的話，會跳警示說那必須寫入預設值
```jsx
componentName.defaultProps = {
	propA: '我是預設字串'
}
```