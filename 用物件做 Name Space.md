## 用物件做 Name Space
> JS 沒有，所以用 [Object](Object.md) 來做！

可以分開同命名的變數或 function 的容器
```js
// 這在使用多個框架或 library 的時候會遇到，比方說不同的 <script> 衝突
// script sourse 1
let language = 'english'
// script sourse 2
let language = 'spanish'

console.log(a)		// 2

const english = {
	name: 'english'
	greet: 'hello'
}
const spanish = {
	name: 'spanish'
	greet: 'hola'
}
```
>[複數 script 時的執行環境](複數%20script%20時的執行環境.md)