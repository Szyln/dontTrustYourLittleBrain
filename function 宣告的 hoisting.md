## function 宣告的 hoisting
function 的 hoisting 會將宣告提到作用域最頂端
```js
fn();					// log "hi"
function fn( {			// hoisting
	console.log("hi");
})
```