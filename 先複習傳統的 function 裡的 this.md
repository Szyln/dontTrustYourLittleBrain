### 先複習傳統的 function 裡的 this
>- [this 的指向](this%20的指向.md)
>- [Function Execution Context](Function%20Execution%20Context.md) 形成 this，指向誰呼叫他的

- this 是指看呼叫時，是誰呼叫這個 function 的
- callback function 通常是在全域下被呼叫的（Function 的參數並不是在 [Function Execution Context](Function%20Execution%20Context.md) 的作用域中）
```js
var name = '全域'
const person = {
  name: '小明',
  callName: function () { 
    console.log('1', this.name); // 1 小明
    setTimeout(function () {
      console.log('2', this.name); // 2 全域
      console.log('3', this); // 3 window
    }, 10);
  },
}
person.callName(); 
```

