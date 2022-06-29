---
title: "function 的 hoisting"
tag: 
- 
---

##  function 的 hoisting

>[但 function expression 不會 hoisting](但%20function%20expression%20不會%20hoisting.md)

function 的 hoisting 會將宣告提到作用域最頂端
```js
fn();					// log "hi"
function fn( {			// hoisting
	console.log("hi");
})
```
