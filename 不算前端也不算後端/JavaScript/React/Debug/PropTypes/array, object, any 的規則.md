### array, object, any 的規則
上述的 `array, object, any` 會提示不該被使用
改為使用
```jsx
// 假設 props 有一個 arrayA, objectB
const arrayA = ['a', 'b'];
const objectB = {
	name: 'a',
	price: 200,
	feature: ['b', 'c', 'd']
}
componentName.propTypes = {
	// array 應該寫清楚 array 內部元素的類型
	arrayA: PropTypes.arrayOf(Proptypes.{寫入這個 array 內的元素類型}),

	// object 同樣應該寫清楚內部 properties 的類型
	objectB: PropTypes.shape({
			name: PropTypes.string,
			price: PropTypes.number,
			feature: PropTypes.arrayOf(PropTypes.string)
	})
}
```