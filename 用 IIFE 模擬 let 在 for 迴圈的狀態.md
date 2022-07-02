### 用 IIFE 模擬 let 在 for 迴圈的狀態 
```js
function buildFn() {
  const arr = []
  // var 跟 let 會有不同效果請注意（跟嚴格模式無關）
  for (var i = 0; i < 3; i++) {
    arr.push(
      (function () {
        console.log(i)
      })(i)							// IIFE
    )
  }

  return arr
}
const buildedArr = buildFn()
```