# Request handling（連接數據庫）
- 使用數據庫多會用到 [[Promise]] 的功能
- 需要使用 [[Mongoose]] 進行讀取、存入資料庫的行為

---
## 網址路徑
用填入資訊建立 object，並且存入資料庫
```
首頁(localhost)/
|- students/	-> 產生變數給 ejs 用			
|	|- insert/  -> accept / reject
|	|- 個別頁面
```

### 將數據庫資料顯示於網頁：
```js
// /students（已登入學生表）
app.get('/student', async (req, res) => {
	let data = await Student.find();
	res.render('students.ejs', { data });
})
```
- 生成 students.ejs：[[編譯 EJS 樣板 res.render()]]
- [[EJS 使用 Mongoose 取得數據庫資料作為變數]]
#### /student/insert 表單
```js
app.get('/students/insert', (req, res) => {
	res.render('studentInsert.ejs');
})
```
- 生成 studentInsert.ejs（表單）
- 供填入[[form]]

##### 處理 POST 請求
```js
app.post('/student/insert', (req, res) => {
	// req.body 是表單資訊
	let { id, name, age, merit, other } = req.body;
	// create an object
	let newStudent = new Student({
		id, name, age, scholarship: { merit, other },
	});
}) 
```
- [[回應表單 (Routing for Query)]]
	- [[POST 表單(express)#使用用戶填入的資訊]]
		- [[從物件中提取屬性到變數中 Destructing an object]]
	- [[透過 Mongoose 存入 MongoDB(Save)]]
#js #npm #node #expressJs #mongoose #database #form #ejs #backEnd 