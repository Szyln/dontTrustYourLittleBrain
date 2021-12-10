# table
## 必要架構
- `tr`(table row)
- `th`(table headings)
- `td`(table data)

每 row 都有一個標題 `th`，其餘都是 `td`

## 語意架構
- `thead`
- `tbody`
- `tfoot`

用於包住不同段落的 `tr`
非必要架構
##  table 用 attribute
- `colspan`
- `rowspan`

value 為數字，代表要橫跨多少 row 或 column
```html
<table>
	<thead>
		<tr>
			<th colspan="2">大標題</th>
		</tr>
	</thead>

	<tr>
		<th>標題</th>
		<td>資料</td>
	</tr>
</table>
```