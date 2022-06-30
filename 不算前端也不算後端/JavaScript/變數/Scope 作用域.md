---
title: "Scope 作用域"
tag: 
- 
---
# Scope 作用域
>- [mdn](https://developer.mozilla.org/en-US/docs/Glossary/Scope)

- 有三種作用域
- 形成作用域可以防止上層讀取內部的宣告（var, let, const, function）
- 但作用域內可以讀取上層的宣告，不論在上層的哪個位置
- [範圍鏈 Scope Chaining](範圍鏈%20Scope%20Chaining.md)：可以[重複宣告一個外層的變數](重複宣告一個外層的變數.md)，宣告會以內部為準

> 作用域的存在可以防止[全域污染](全域污染.md)


## 類型
> Scope 的生成時機與 [執行環境 Execution Context](執行環境%20Execution%20Context.md) 有關

- [Global Scope](Global%20Scope.md)
- [Function Scope](Function%20Scope.md)
- [Block Scope](Block%20Scope.md)

|作用域類型|var|let|const|
|-|:-:|:-:|:-:|
|Global|O|O|O|
|Function|O|O|O|
|Block|==非嚴格模式 X== / 嚴格模式 O|O|O|



#js #variable #scope