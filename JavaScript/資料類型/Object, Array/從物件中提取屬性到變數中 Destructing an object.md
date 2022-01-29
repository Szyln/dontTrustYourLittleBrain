# 從物件中提取屬性到變數中 Destructing an object
- 長相像有大括號的變數
- 可以把物件的屬性提出來使用，不用重複用點記法點屬性
```js
let {} =						 // 防失智搜尋用
let {提出來用的物件屬性1, 提出來用的物件屬性2 ...} = 物件;

```
```js
let Sam = {
	name: 'Sam',
	age: 25,
	friends: {
		friendName: 'Mike',
	}
}

// 舊作法
// let name = Sam.name;
// let age = Sam.age;
// let firendName = Sam.friends.name;

// 新作法
let {name, age} = Sam;			// {} 批次處理
let {firendName} = Sam.friends;
```
# Destructing Assignment
```js
// array
[a, b, ...rest] = [10, 20, 30, 40, 50];
console.log(a); // 10
console.log(b); // 20
console.log(rest); // [30, 40, 50]

// object
({a, b, ...rest} = {a: 10, b: 20, c: 30, d: 40});
console.log(a); // 10
console.log(b); // 20
console.log(rest); // {c: 30, d: 40}
```
#mango #js #object 