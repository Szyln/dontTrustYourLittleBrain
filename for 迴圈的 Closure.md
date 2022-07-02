## for 迴圈的 Closure
```js
function buildFn() {
  const arr = []
  // var 跟 let 會有不同效果請注意（跟嚴格模式無關）
  for (var i = 0; i < 3; i++) {
    arr.push(
      function () {
        console.log(i)
      }
    )
  }

  return arr
}
const buildedArr = buildFn()
buildedArr[0]()
buildedArr[1]()
buildedArr[2]()
// var: log 三次 3
// let: log 0, log 1, log 2
```
### var
- `push` 的內容是 `function` 的宣告，沒有執行
  - 執行的時機點是在 `buildFn()` 結束後，所以 Closure 讀到的 `i` 是 for 迴圈結束後的 `3`

>[用 IIFE 模擬 let 在 for 迴圈的狀態](用%20IIFE%20模擬%20let%20在%20for%20迴圈的狀態.md)

### let
- 使用 `let` 的話，每次 for 更新後 block 是獨立的作用域，`buildedArr[i]` 抓得到每一次的 `i` 值
- [用 IIFE 模擬 let 在 for 迴圈的狀態](用%20IIFE%20模擬%20let%20在%20for%20迴圈的狀態.md)：結果同 `let`
 
