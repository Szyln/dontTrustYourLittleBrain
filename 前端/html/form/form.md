# form
## form tag
與後端（數據庫）相關的標籤
需要傳送的資料都要寫在這個標籤裡，不然不會傳輸
```html
<form
	action="資料傳送的目的地（連結後端）" 
	method="預設GET（公開），POST（非公開）"
>
</form>
```
- [[label]]
- [[input]]
- [[select & datalist]] 
- [[textarea]]
- [[button]] 不建議用，不是 form 專用 type submit 的 input，button 在有 JS 客製化 event 時用

20:17的部份重聽


## 細心的表單
金流網站最細心
- 綠界藍心
- 金流御三家 - 紅綠藍


## 關於更改表單樣式
表單樣式的修改，在不同版本的系統可能都不一樣
不容易改得動


## 表單的運作以及標準起手式

表單包含元素：

-   [[form]] 標籤
    -   action → API 網址
    -   method → 對應方法
-   input 標籤
    -   type → input 的類型
    -   name → 對應的後端欄位
    -   id → input 的唯一標記
    -   placeholder → 給予用戶的說明文字
-   label 標籤
    -   針對 input 的描述
-   button 標籤
    -   type → 按鈕類型，預設為 submit


#form #html