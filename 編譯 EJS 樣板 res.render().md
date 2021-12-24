# 編譯 EJS 樣板res.render()
> ejs 檔案要放在[[樣板：views 資料夾]]裡
```js
// 單純編譯
res.render('page.ejs')
// 搭配變數
res.render('page.ejs'), { name }}
```

>- [[生成 EJS 樣板可用的變數]]
> `{name}` 是 `{ name: name }` 的語法糖

#npm #gulp #html #js #ejs #expressJs 