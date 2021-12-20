## EJS 撰寫
EJS 可以當成就是在 JS 環境寫 HTML，所以也可以在裡面寫 JS
```ejs
// 要顯示出來的變數
<標籤><%= 要取得這個值到 HTML 的話 %></標籤>

// 單純寫
<% 撰寫純 JS code 的話 %>
```
### 範例
#### 單純用變數
>使用已經生成的 name 變數：[[生成樣板可用的變數：Routing for pattern]]
```ejs
// person.ejs
// 網址打什麼都會顯示在 name 變數裡面
<h1><%= name %></h1>
```
#### for 迴圈
`i` 會顯示在 HTML，要加 `=`
```ejs
<body>
	<%for (let = 0; i < 10; i++) {%>
		<p><%= i %><p>
	<% } %>
</body>
```