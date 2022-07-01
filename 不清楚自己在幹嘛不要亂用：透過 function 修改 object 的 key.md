### 不清楚自己在幹嘛不要亂用：透過 function 修改 object 的 key
```js
const objA = {
	a: 1,
	b: 2
}
const objB = objA
// 不清楚自己在幹嘛不要亂用
const fn = (obj) => {
  obj.a = 2; 
}

// 傳參考特性，objA, objB 都會改到
fn(objB)
```