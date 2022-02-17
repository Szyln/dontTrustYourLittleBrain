# navbar
```html
<nav>

</nav>
```

## nav 用 class
```html
<nav class="navbar navbar-light bg-secondary-light navbar-expand-lg">
	<!-- navabr: 主要 class
	<!-- navbar-light：淺字（配合深底）
	<!-- bg-<theme-color（自訂變數的話，要設定API）> -->
	<!-- navbar-expand-<breakpoint>：設定什麼時候要將細項收起來 -->
</nav>
```


## .container
```html
<nav>
	<div class="container">
			<!-- 內容不貼邊 -->
	</div>
</nav>
```

## 子元素
### .navbar-brand
對 `<a>` 最適用
```html
<a class="navbar-brand" href="/">DOYOGA</a>
```
加入 `<img>` 
```html
<a class="navbar-brand" href="#">
	<img src="/docs/5.0/assets/brand/bootstrap-logo.svg" alt="" width="30" height="24">
</a>
```
`<img>` + 文字
```html
<nav class="navbar navbar-light bg-light">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">
      <img src="/docs/5.0/assets/brand/bootstrap-logo.svg" alt="" width="30" height="24" class="d-inline-block align-text-top">
      Bootstrap
    </a>
  </div>
</nav>
```

### navbar-toggler
開關細項的按鈕
```html
<button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
	<span class="navbar-toggler-icon"></span>
</button>
```
### .navbar-nav
- 細項群組（會被收起來的）
- 細項：`.nav-item`
- `ul` 可以替換成 `div`（沒有 `li` 所以不使用 `nav-item`）
```html
<ul class="navbar-nav me-auto mb-2 mb-lg-0">
	<li class="nav-item">
		<a class="nav-link active" aria-current="page" href="#">Home</a>
	</li>
</ul>
```
外面要用 `.collapse.navbar-collapse` 兩個 class 包起來觸發效果
```html
<div class="collapse navbar-collapse" id="navbarSupportedContent">
</div>
```
>[srolling（收起來的內容的滾動效果）](https://bootstrap5.hexschool.com/docs/5.0/components/navbar/#scrolling)
>加入一個選填的屬性 .navbar-scroll 來設置 max-height 

#### .nav-item
細項 nav-item
```html
<li class="nav-item">
	<a class="nav-link active" aria-current="page" href="#">Home</a>
</li>
```
#### nav-link
特指在 navbar 內的連結設定（不會影響到其他 btn-link）
- `.active` 代表當前頁面（搭配 `aria-current="page"` 屬性使用）
```html
<a class="nav-link active" aria-current="page" href="#">Home</a>
```
##### dropdown
在 `.nav-item` 內可以使用 `.dropdown`
```html
<li class="nav-item dropdown">
  <a class="nav-link dropdown-toggle" href="#" id="navbarDropdownMenuLink" role="button" data-bs-toggle="dropdown" aria-expanded="false">
    Dropdown link
  </a>
  <ul class="dropdown-menu" aria-labelledby="navbarDropdownMenuLink">
    <li><a class="dropdown-item" href="#">Action</a></li>
    <li><a class="dropdown-item" href="#">Another action</a></li>
    <li><a class="dropdown-item" href="#">Something else here</a></li>
  </ul>
</li
```
## .form
也可以放入表單、按鈕等內容，視有沒有收合需求放入 `.navbar-nav` 內
```html
<form class="container-fluid justify-content-start">
  <button class="btn btn-outline-success me-2" type="button">Main button</button>
  <button class="btn btn-sm btn-outline-secondary" type="button">Smaller button</button>
</form>
```

#bs/component 