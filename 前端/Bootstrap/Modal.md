# Modal


## 運作
- 除 html, css 也需要 js 才能運作
- 啟動時無法滾動 `body` 內容
- 只能一個同時用單一 `modal`

## 基本組合

| 屬性 | 按鈕                   | Modal |
| ---- | ---------------------- | ----- |
|      | `data-bs-toggle=modal` | ``      |


```html
<!-- 啟動 modal 按鈕 -->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
  Launch demo modal
</button>

<!-- Modal -->
<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        ...
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
      </div>
    </div>
  </div>
</div>
```

- 
#css/scss #bs/component/modal