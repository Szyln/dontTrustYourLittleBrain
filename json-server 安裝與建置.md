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
	// 這個是範例，可按照這個格式，依自己的需求寫
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
- 開機完就會得到如下回應，可以看到他有提供 [endpoint](endpoint.md) 作使用
- `Resources` 的三個 endpoint 剛好對應上面的 `db.json` 裡的三個物件屬性 `post`, `comments`, `profile`
- 可以進去這些 [[endpoint]] 看內容，或是用 [Postman](Postman.md) 查看
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