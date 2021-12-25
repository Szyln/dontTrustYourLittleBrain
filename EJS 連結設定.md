# EJS 連結設定
```ejs
<a href="/students">回到學生列表</a>
```

```ejs
<ul>
	<% data.forEach(student=> { %>
	<li><a href="/students/<%= student.id %>">
	<%= student.name %>, 編號<%= student.id %>
	</a></li>
	<% }) %>
</ul>
```