# EJS 回應表單([[回應表單 (Routing for Query)]])
```html
// index 上的表單
<form action="/response" method="GET">

	<label for="name">Your Name</label>
	<input type="text" id="name" name="name">

	<label for="age">Your Age</label>
	<input type="text" id="age" name="age">
	
	<input type="submit">Submit</input>

</form>
```

```js
// app.js
app.get("/response", (req, res) => {
	let { name, age } = req.query		// get 表單
	res.render("respond.ejs")
})
```
> [[從物件中提取屬性到變數中 Destructing an object]]
```html
// respond.ejs
<h1>表單已送出</h1>
<ul>
	<li>你的名字：<%= name %></li>
	<li>你的年齡：<%= age %></li>
</ul>
```