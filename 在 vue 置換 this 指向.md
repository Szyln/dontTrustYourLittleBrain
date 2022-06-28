## 在 vue 置換 this 指向
- 先讓 this 設定指向其他變數：vm (Vue 中指的 ViewModel)
- 使用箭頭函式

### 先讓 this 設定指向其他變數：vm 
在 function 外面抓取外部的 vm
再將 vm 帶進去 function 內部
```js
var obj4 = {
  someone: '物件 4',
  fn() {
    const vm = this; // vm 在 Vue 中意指 ViewModel
    setTimeout(function () {
      console.log(vm.someone);
    });
  }
}
obj4.fn();
```

### 直接改用箭頭函式
用箭頭函式的特性，會直接讀取外層的 this
```js 
var obj4 = {
  someone: '物件 4',
  fn() {
    setTimeout(() => {
      console.log(this.someone);
    });
  }
}
obj4.fn();
```