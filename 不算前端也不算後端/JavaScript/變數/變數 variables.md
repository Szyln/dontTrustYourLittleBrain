---
title: "變數 variables"
tag: 
- 
---
# 變數
有三種變數，[var, let, const 的差異](var,%20let,%20const%20的差異.md)
![](var,%20let,%20const%20的差異.md#^1f3f2a)


## 使用步驟
### declaration 宣告
宣告未賦值（指派、[初始化(initializer)](初始化(initializer).md)）

> 只有宣告時可能長什麼樣子：[[undefined]]

### assignment 指派、賦值
[Assignment Operator(=)：指派、賦值、初始化](Assignment%20Operator(=)：指派、賦值、初始化.md)：指派，右邊指派到左邊，不是等於
- `let` 宣告完可以再指派，`const` 不行

```js
// 宣告＋賦值
let x = 10;
// 屬性
x = 5;

// 也可以這樣快速賦值好幾個
var a = 1, b = 2, c = 4 
console.log(a, b, c)
```

### 屬性與變數的差異
- 屬性可以被刪除 (a = 1)
- 變數無法被刪除 (var a = 1)

## 作用域
[[var, let, const 的差異]]內詳細

## 命名規則
- [ ] 開頭數字
- [ ] 包含 `-`
- [x] camel case
- [x] 包含 `_`



#js #variable
