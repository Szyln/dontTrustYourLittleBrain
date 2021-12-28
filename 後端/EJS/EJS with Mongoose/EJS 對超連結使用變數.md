# EJS 對超連結使用變數
網址上也可以使用變數
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


#js #npm #node #expressJs #mongoose #database #form #ejs #backEnd 