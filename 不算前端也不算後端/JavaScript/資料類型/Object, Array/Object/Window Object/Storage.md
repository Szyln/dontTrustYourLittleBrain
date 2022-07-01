---
title: "Storage"
tag: 
- js/object/window
---
# Storage
- 瀏覽器的暫存空間（不是 [[Database 數據庫]]）
- 放一些很簡單的資料，跟資安無關的內容
- 在 devtools 可以找到

### 使用方式
>[讓 JSON（或是字串格式） 與 JS 讀得懂彼此：格式轉換](讓%20JSON（或是字串格式）%20與%20JS%20讀得懂彼此：格式轉換.md)

- 放入：JS 用 object 格式放進去
- 進去之後全部都會變成 string
- 取出：使用 [JSON.parse(JSON String)：JSON string to JS 資料型別](JSON.parse(JSON%20String)：JSON%20string%20to%20JS%20資料型別.md) 還原成 JS 看得懂的型別 


## Storage 的 CRUD
- [[setItem(key, value)]]
- [[getItem(key)]]
- [[removeItem(key)]]
- [[clear()]]

> key 是不能重複的