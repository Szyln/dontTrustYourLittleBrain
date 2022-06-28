### function 被 object 呼叫
> 最常見的 this 用法

function 在 object 中，function 中的 this 指向 object 

```js
var obj = {
  someone: '物件',
  callSomeone() {
    console.log(this.someone);	// this 指該物件
  }
}
obj.callSomeone();
```