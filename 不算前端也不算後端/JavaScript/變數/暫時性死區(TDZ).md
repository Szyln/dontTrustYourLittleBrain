---
title: "暫時性死區(TDZ)"
tag: 
- js/variable/scope
---
## 暫時性死區 (TDZ, Temporal Dead Zone)

>會 [Hoisting](Hoisting.md) 就不會 TDZ（沒有使用後宣告的概念）

![](https://i.imgur.com/b6JIhZ5.png)
- [TDZ：作用域中 let, const 使用後初始化（這邊好像是指宣告）](TDZ：作用域中%20let,%20const%20使用後初始化（這邊好像是指宣告）.md)

> 重點不是重複宣告，是使用後宣告

### 注意
- 這不是 TDZ：[重複宣告參數](重複宣告參數.md)
- 「在該作用域」要使用後宣告才會 TDZ：[重複宣告一個外層的變數](重複宣告一個外層的變數.md)
- [外層的宣告，不論順序，內層都可以讀（這不是 hoisting）](外層的宣告，不論順序，內層都可以讀（這不是%20hoisting）.md)







>[但 function expression 不會 hoisting](但%20function%20expression%20不會%20hoisting.md)
