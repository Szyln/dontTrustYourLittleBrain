---
title: "__proto__"
tag: 
- 
---

##  `__proto__`
>[該來理解 JavaScript 的原型鍊了](https://blog.techbridge.cc/2017/04/22/javascript-prototype/)

> 更好的寫法是 `getPrototypeOf()`



proto 記載該物件的 [Prototype](不算前端也不算後端/JavaScript/物件導向%20OOP/Prototype.md)（包含原型的屬性）
```js
// Prototype
function Person(name, age) {
	this.name = name
	this.age = age;
}
// 幫 Prototype 加一個屬性（可以共用）
Person.prototype.selfIntro = function () {
	console.log(`Hi, my name is ${this.name}, I am ${this.age}`);

let sam = new Person('Sam', 23)

console.log(sam.__proto__);
```
![](https://i.imgur.com/tEAQHh2.png)

物件實例的 `__proto__` 會等於他繼承的 `.prototype`
```js
console.log(sam.__proto__ === Person.prototype);
```