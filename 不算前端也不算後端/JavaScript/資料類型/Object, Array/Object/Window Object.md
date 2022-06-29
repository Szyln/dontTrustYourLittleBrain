---
title: "Window Object"
tag: 
- js/object/window
---
# Window Object
程式碼執行時，[Global Execution Context](Global%20Execution%20Context.md) 自動生成的物件，等於 Global 的 [[this]]

```js
var a = 1
let b = 2
const c = 3
window.a // 1
window.b // undefined
window.c // undefined
```

## Properties
- Console
- Document
- [[Storage]]
	- [[Local Storage]]
	- [[Session Storage]]

#js #window #object