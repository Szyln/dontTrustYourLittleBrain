# let, const, var 的差異｜筆記 by Sz
###### tags: `Sz` `課前` `Vue新手夏令營` 

- [Vue 新手夏令營 課程頁面](https://hackmd.io/@dbFY0UD9SUeKmNXhWf01ew/BkJoW-hn_/%2FC05go-8iTSS-nrMwKU22kA)
- [:sun_with_face:筆記入口](/2JiZbCPdR0G4p5fNycPmTg)


::: info
- 為什麼要宣告變數
    - 避免全域、區域污染
    - 屬性與變數的差異
        - 屬性可以被刪除 (a = 1)
        - 變數無法被刪除 (var a = 1)

:::


# 辭法作用域
````
// var 作用域在程式碼寫完的當下就確定了 
// #1 
var a = '全域';
function fnA() {
	console.log('a = ' + a);    // a = 全域
}
	
function fnB() {
	var a = 'local';
	fnA();                      // a = 全域
	console.log('a = '+ a);     // a = local
}
		
console.log(a)              // a = 全域
````

## var 的特性
### function 作用域
- 在 function 內的 var，上層讀不到
- 在 {}(block) 內的 var，上層讀得到
### for...
- for 設定的 var，執行後的外層會讀到結果
- 設定 var 變數的 for 內部若有 setTimeout() ，也會跟迴圈一樣執行同等次數，但都是最終結果（非同步，目前還搞不懂為什麼要這麼用）
### hoisting

  

## let 與 var 的差異

### 作用域不同 var function, let block
- **let 的作用域只在內部**
- **設定 let 的 for 內部若有** setTimeout() ，則不會在 for 執行完後才執行，會正常顯示 for 迴圈
- 不會在 window 上

### 不可重複宣告
````
var a = 1;
var a = 0;      // 可
````
````
let a = 1;
let a = 0;      // 不可
a = 0;          // 可
````
### hosting
- 暫時性失去
	- function 已經從外部傳入參數時，又在內部重新宣告 let 參數的話，function 內部重新宣告前該參數會暫時性失去

### const 與 let 不同之處
````
// 不可重複覆值
const a = 1;
a = 2;        // 不可
````
  

### 陷阱 const 與 let 的選擇
- const 不可重複


### 但 const 內有物件
- 物件的屬性是可以改的（物件傳參考）
- 但直接改const 成其他物件是不行的（物件傳參考）

  

## 其他
- undefined 跟 not undefined
````
var a         // a = undefined
 // a is not undefined
````
- debugger  

  

  


#js #vue