---
title: "Prototype Inheritance"
tag: 
- 
---
# Prototype Inheritance（原型繼承）
> - [Inheritance](Inheritance.md)
> - 另外一種繼承：古典繼承，見於 C++ 等語言，比較複雜


- JavaScript 的 [物件導向 OOP](不算前端也不算後端/JavaScript/物件導向%20OOP/物件導向%20OOP.md) ，有 [Inheritance](Inheritance.md) （繼承）的特性
- 與其他語言不同，是透過 [Prototype](不算前端也不算後端/JavaScript/物件導向%20OOP/Prototype.md) 的設定來達成
- 從 [Prototype](不算前端也不算後端/JavaScript/物件導向%20OOP/Prototype.md) 來創造的 [物件實例](物件實例.md) 就會繼承 [Prototype](不算前端也不算後端/JavaScript/物件導向%20OOP/Prototype.md) 的方法



## 原有的
Constructor 負責放每個物件內容都不一樣的部份
一樣的部份就放到 [Prototype](Prototype.md) 裡面，節省記憶體
繼承時兩個部分都要處理

### [[Constructor]]
```js
// Constructor
function Person(name, age, height) {	// 大寫開頭
	console.log(this);					// 指向 object
	this.name = name,
	this.age = age,
	this.height = height

}

let StudentSam = new Student("Sam", 20, 140)	// this 指物件本身
```

### [[Prototype]]
```js
// 共用的函式拉出來到 prototype 內
// 注意是 simple call
Person.prototype.sayHi = function() {
	console.log(this.name + " says hi.");	// 目前 this 指向全域
}
```

## 繼承的
### Constructor
使用 [function.call(obj, arguments)](function.call(obj,%20arguments).md) 的方法，繼承 [[Prototype Inheritance#原有的#Constructor]]（但目前 Prototype 沒有被繼承）
```js
// 從 Person 繼承過來的新 Constructor
// 用 call 將 Person 繼承過來
// 新增兩個只有 Student 才有的參數
function Student(name, age, height, major, grade) {

	// 將原本的 this 置換成這裡的 this
	Person.call(this, name, age, height); 	// 更新 this 的指向
	this.major = major,
	this.grade = grade
	
}

let StudentSam = new Student("Sam", 20, 140, "math", 2);	// this 指物件
```
#### 備註：沒效率的作法
```js
// 從 Person 繼承過來的新 Constructor
// 把 Person 的內容照抄過來
function Student(name, age, height, major, grade) {
	this.name = name,
	this.age = age,
	this.height = height,
	
	this.major = major,
	this.grade = grade,
	
}
let StudentSam = new Student("Sam", 20, 140, "math", 2);	// this 指物件
```
### [[Prototype]]
接下來處理 [[Prototype Inheritance#原有的#Prototype]]，使用 [[create()]] 增加可讀性，必且讓新 Constructor 的 prototype 等同於原 Constructor
```js
// 讓新 Constructor 的 prototype 等同於原 Constructor
Student.prototype = Object.create(Person.prototype);

// 也可以繼續新增 Student 獨有的 Prototype
Student.prototype.study = function() {
	console.log("I'm studying");
} 

let Mike = new Student("Mike", 10, 140, "Design", 1);
```
#### 備註：沒效率的作法
手動把 Student 新增 prototype，但這樣會導致修改 Prototype 的時候，每行都要修改(`Person.prototype.sayHi` 跟 `Student.prototype.sayHi`...)

```js
Student.prototype.sayHi = function() {
	console.log(this.name + " says hi.");
}
```

#js #advanceJs #object #oop

