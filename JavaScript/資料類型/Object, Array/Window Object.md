# Window Object
## Properties
- Console
- Document
- Storage
	- LocalStorage
	- Session Storage

## Storage
有兩種
	- LocalStorage
	- Session Storage
	
瀏覽器的暫存空間（不是 [[Database 數據庫]]）
放一些很簡單的資料，跟資安無關的內容

- 都是 object
- 在 devtools 可以找到


### Storage 資料的使用（[[深層拷貝、非 string 類型的資料類型轉換]]）





### Storage 的 methods 
- setItem(key, value)
- getItem(key)
- removeItem(key)
- clear()

> key 是不能重複的


#### setItem(key, value)
儲存內容進去
#### getItem(key)
取得內容
#### removeItem(key)
刪除指定內容
#### clear()
清空

### session storage 跟 local storage 的差別
#### session storage
瀏覽器關掉就會清空
#### local storage
關掉不會清空，除非主動用 `clear()`清空

#js #window #object