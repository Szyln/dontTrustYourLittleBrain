---
title: "json-server 不會後端也可以開 API"
tag: 
- 
---

##  json-server 不會後端也可以開 API
>[json-server - 讓你不會後端也能開 API](https://youtu.be/9TAanXxNvEI)

### 安裝
```shell
# 全域安裝
npm install -g json-server
```

### 建置
- 建立專案資料夾放 `db.json` （就是拿來放資料的地方，當資料庫用）
- `db.json` 放入資料庫內容
	```json
	// db.json
	{
		"posts": [
			{ "id": 1, "title": "json-server", "author": "typicode" }
		],
		"comments": [
			{ "id": 1, "body": "some comment", "postId": 1 }
		],
		"profile": { "name": "typicode" }
	}
	```

### 開機資料庫
這樣前端發送 request 的時候資料庫才會有反應
```shell
json-server --watch db.json
```
開機完就會得到如下回應，可以看到他有提供 [endpoint](endpoint.md) 作使用
`Resources` 的三個 endpoint 剛好對應上面的 `db.json` 裡的三個物件屬性 `post`, `comments`, `profile`
```shell
 \{^_^}/ hi!

  Loading db.json
  Done

  Resources
  http://localhost:3000/posts
  http://localhost:3000/comments
  http://localhost:3000/profile

  Home
  http://localhost:3000

  Type s + enter at any time to create a snapshot of the database
  Watching...

GET /posts 200 8.070 ms - 77
```

### [Postman](Postman.md) 測試
![](Pasted%20image%2020220520195407.png)
- 最左邊選擇要發送的 Request
- 中間輸入 endpoint
- 發送出去就會得到結果了

這樣就可以拿來練習基本的 CRUD 了

### 可用的 query
> [endpoint](endpoint.md)：query 就是 endpoint 中 `?` 後面那串

#### Filter
尋找對應符合 key 的 value
```
GET http://localhost:3000/posts/posts?title=json-server&author=typicode
```
```
// 其他 query 像這樣
GET /posts?id=1&id=2   
GET /comments?author.name=typicode`
```
#### 搜尋全文
```
GET http://localhost:3000/posts/posts?p=json
```
#### 頁數、限定前 X 筆
- `_page`：頁數
- `_limit`：限定前 X 筆
```
GET /posts?_page=7
GET /posts?_page=7&_limit=20
```

#### 邏輯
- `_gte`：>=
- `_lte`：<=
- `_ne`：!==
- `_like`：filter，包含字串

```
GET /posts?views_gte=10&views_lte=20
```
```
GET /posts?title_like=server
```

#### sort 排序
- `_sort`：
- `_order`：預設升冪 ( `asc` )
	- `_order=asc`：升冪
	- `_order=desc`：降冪

```
GET /posts?_sort=views&_order=asc
GET /posts/1/comments?_sort=votes&_order=asc
```
##### 複數的欄位排序
```
GET /posts?_sort=user,views&_order=desc,asc
```
### 指令

