---
title: "Scope 作用域"
tag: 
- 
---
# Scope 作用域
>- [mdn](https://developer.mozilla.org/en-US/docs/Glossary/Scope)

有三種作用域，形成作用域的時候，可以防止上層讀取內部的宣告（var, let, const, function）

> 作用域的存在是為了防止[全域污染](全域污染.md)



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