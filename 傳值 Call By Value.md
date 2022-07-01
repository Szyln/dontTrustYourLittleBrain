### 傳值 Call By Value
- 把 value 傳到另一個**記憶體位置**的 value 上，是 copy 非 link 
- JS 中的純值（[[原始資料類型 Primitive Data Types]]）就是這個特性(Boolean、Null、Undefined、Number、String)
- 彼此只有 copy 關係，所以 copy 完後，其中一方被更改，不會影響到另一方