## new Object()
- [新增物件](新增物件.md) 的一個方法（[物件字面值](物件字面值.md)比較好用）
- [物件導向 OOP](物件導向%20OOP.md) 可能比較需要這個功能
```js
// 新增一個 obj1 的空物件

const obj1 = new Object()
// obj1 = {}
```

### 也可以在物件中新增物件
```js
const obj1 = {
}

// obj2 的新屬性：c: {}
obj2.c = new Object();
```

>所以在 JS 中，new 是保留字，不能拿來命名