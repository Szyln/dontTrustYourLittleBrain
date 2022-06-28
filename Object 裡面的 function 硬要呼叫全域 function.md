#### Object 裡面的 function 硬要呼叫全域 function

callSomeone 還是全域的 function

```js
function callSomeone() { console.log(this) }

var obj3 = {
  someone: '物件 3',
  fn() {
    callSomeone(); // 通常平常不會這樣去取用 this
  }
}
obj3.fn();  // callSomeone 的 this 還是全域
```

>可以呼叫 function 的只有 object, global 兩種