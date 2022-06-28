#### Object 中還有 Object

```js
var wrapObj = {
  someone: '外層物件',
  callSomeone: function callSomeone() {console.log(this.someone);}, 
  innerObj: {
    someone: '內層物件',
  callSomeone: function callSomeone() {console.log(this.someone);},
  }
}
wrapObj.callSomeone()						// log 外層物件，this 指 wrapObj
wrapObj.innerObj.callSomeone();	// log 內層物件，this 指 innerObj
```