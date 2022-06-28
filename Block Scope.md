---
title: "Block Scope"
tag: 
- 
---

##  Block Scope
>[block](block.md)


非嚴格模式中很容易出現[全域污染](全域污染.md)的狀況

- [非嚴格模式的 block](非嚴格模式的%20block.md)：var, function 不形成 [Scope 作用域](Scope%20作用域.md)，[全域污染](全域污染.md)
- [嚴格模式的 block](嚴格模式的%20block.md)：var, let, const, function 形成 [Scope 作用域](Scope%20作用域.md)


| block 內宣告會不會全域污染 |  var   |  let  | const | function |
| -------------------------- | :----: | :---: | :---: | :------: |
| 嚴格模式                   |   否   |  否   |  否   |    否    |
| 非嚴格模式                 | ==會== |  否   |  否   |  ==會==  |

