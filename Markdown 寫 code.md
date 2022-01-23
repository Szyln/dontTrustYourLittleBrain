# Markdown 寫 code
## 內文 code
`i = 3` ：前後各一個可以寫內文用的 code（比較不好整理的寫法，建議用下面這個）

## 區塊 code
```js
// 前後各三個 ` 包起來可以寫一塊程式碼
// 上面的點後面可以加上目前正在寫的語言
let i = 1;
```


```
// 沒有加就會都是單色
i = 1
```
```py
i = 2
```

```js
mongoose.connect(process.env.DB_CONNECT).then(() => {
  console.log('成功連上 mongoDB Atlas');
}).catch((err) => {
  console.log(err);
})
```