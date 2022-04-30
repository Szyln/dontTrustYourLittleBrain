---
title: "Label must have associated control"
tag: 
- debug/lint
---
## Label must have associated control
>[ESLint](ESLint.md)

這個風格規則建議 input 放在 label 內，（[Bootstrap](前端/Bootstrap/Bootstrap.md) 的設定中與此衝突，配合 BS 的時候我會 disable 這個規則）

> [Label must have associated control](https://stackoverflow.com/questions/62306461/label-must-have-associated-control)
> 
> To associate a label with another control implicitly, the **control element must be within the contents of the LABEL element**.
> 
> Source: [W3.org, Forms in HTML document - 17.9 Labels](http://www.w3.org/TR/html4/interact/forms.html#h-17.9)

