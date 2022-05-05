---
title: "axios"
tag: 
- js/api
- js/json
- js/ajax
---
## axios
>- [AJAX](後端/API/AJAX/AJAX.md)
>- [npm](https://www.npmjs.com/package/axios)

### 或是掛 cdn 的方法
```html=
<script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
```

## 取得遠端資料
```javascript=
axios.get('https://randomuser.me/api/')
  .then(res => {
  // 通常 res 會是多項資料，取出需要的部份
    console.log(res.data.results);  
  })
   // err.response 是固定用法
  .catch(err => {
    console.log(err.response); 
  })
```  
