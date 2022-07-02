### return function 的 closure
參數、宣告變數、宣告 function 都可以
```js
function fn1(a) {
  let b = 'b'
  function fnInFn1() {
    console.log('fnInFn1 in fn1');
    
  }
  return function fn2(c) {
    console.log(a, b, c);   // 可以讀取
    fnInFn1()   						// 可以執行
  }
}
const fn3 = fn1('a')
fn3('c')			
// log a b c
// log fnn in fn1
```