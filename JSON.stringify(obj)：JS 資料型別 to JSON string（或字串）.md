## JSON.stringify(obj)：JS 資料型別 to JSON string（或字串）
- [Object](Object.md), [Array](Array.md) 轉換後：型別是 [String](String.md)，長相是 JSON
- 非 [Object](Object.md) 轉換後：純字串

```js
console.log(JSON.stringify({
	name: 'sam',
	age: 12
}))
// log 字串 {"name":"sam","age":12}
```