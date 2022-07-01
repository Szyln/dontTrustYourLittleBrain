---
title: "讓 JSON（或是字串格式） 與 JS 讀得懂彼此：格式轉換"
tag: 
- 
---

##  讓 JSON（或是字串格式） 與 JS 讀得懂彼此：格式轉換
> JSON 不是 JS 的內容，對 JS 來說 JSON 跟純文字沒兩樣


JS 有提供可以互相格式轉換的功能，==但不限於 JSON，string 也可以==拿來轉換成其他的 JS [資料型別](資料型別.md)

- [JSON.stringify(obj)：JS 資料型別 to JSON string（或字串）](JSON.stringify(obj)：JS%20資料型別%20to%20JSON%20string（或字串）.md)
- [JSON.parse(JSON String)：JSON string to JS 資料型別](JSON.parse(JSON%20String)：JSON%20string%20to%20JS%20資料型別.md)

### 使用場合
- [Storage](Storage.md) 的資料：因為 Storage 的資料都是以純文字的方式儲存的
- JSON to JS [資料型別](資料型別.md)
- 純文字轉換成 JS [資料型別](資料型別.md)
- 取消傳參考：[物件不要傳參考的時候：深層、淺層拷貝](物件不要傳參考的時候：深層、淺層拷貝.md) 的 [深層拷貝：暴力取消傳參考特性](深層拷貝：暴力取消傳參考特性.md)

