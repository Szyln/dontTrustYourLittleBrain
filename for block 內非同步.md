## for block 內非同步
### var
var 運算結束後執行
```js
// 不要這樣做
for (var i = 0; i < 10; i++) {
    setTimeout(() => {
        console.log(i);
    }, 0);
} // log 10 十次
```
### let
按照 for 的規則
```js
for (let i = 0; i < 10; i++) {
    setTimeout(() => {
        console.log(i);
    }, 0);
} // log 0 ~ log 9
```