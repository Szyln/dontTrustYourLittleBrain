# 如何使用 JavaScript 製作分頁效果
[簡報連結](https://hackmd.io/@SidStraw/Sy1Ihg_Bt#/)
[範例](https://github.com/SidStraw/js-pagination-simple)
[套件專案](https://github.com/SidStraw/Pagination-UI-LESS)
[套件CDN](https://cdn.jsdelivr.net/npm/pagination-ui-less)
[講師部落格：這可要好好管管](https://sid.tw/)
[Postman 如何使用 HMAC 以 TDX API 為例](https://hsiangfeng.github.io/other/20210928/2005731696/)
[完全解析 JavaScript import、export](https://wcc723.github.io/development/2020/03/25/import-export/)
[什麼是 ESM(ES6 Modules or JavaScript Modules) 呢？](https://hsiangfeng.github.io/javascript/20210424/616364031/)
## 綱要
- 設計思路
- 知識點補充
- DOM render 處理
- pagination 處理
- history API
- 延伸
- Q&A

## 設計思路
### 為什麼要做分頁
資料量太多，渲染時負荷量太大會跑很慢
-   一次性取得所有資料
-   批次獲取各頁面資料
### 分頁獲取的前提
-   API 有回傳資料總筆數

## 知識點補充
### [[Event Bubbling]]
```js
paginationElement.addEventListener('click', e => {
  const target = e.target.dataset
  const currentTarget= e.currentTarget.dataset
})
```

### Dataset
```html
<a
  href="?page=1"
  onclick="return false"
  data-action="setPage"
  data-value="1"
>
  1
</a>
```
```js
paginationElement.addEventListener('click', e => {
  const { action, value } = e.target.dataset
  action === 'setPage' // true
  value === '1' // true
})
```

### ES module
```html
<script type="module" src="./simple_all.js"></script>
```
```js
// simple_all.js
import { getParkingApi } from './module/service.js'
```
```js
// module/service.js
export function getBikeApi() {}
export function getParkingApi() {}
export default { getBikeApi, getParkingApi }
```
### 解構賦值
如果 funciton 要訂 3 個以上的參數，就不會想要一個一個訂了
```js
// 解構賦值：直接送一個物件給他
function foo({ a = 1, b = 1, c }) {}
```
```js
// 沒有帶 b 參數，會給宣告時的預設值 1
foo({
  a: 10,
  c: () => {},
})
```
### 剛剛 Dataset 講到的範例
```
paginationElement.addEventListener('click', e => {
  const { action, value } = e.target.dataset
  action === 'setPage' // true
  value === '1' // true
})
```

### 展開運算子
... 把陣列解開來
```js
Math.max(1, 2, 3) === Math.max([1, 2, 3]) //false
Math.max(1, 2, 3) === Math.max(...[1, 2, 3]) //true
```
```js
const arr1 = [1, 2, 3]
const arr2 = arr1
arr1 === arr2 // true

const arr1 = [1, 2, 3]
const arr2 = [...arr1]
arr1 === arr2 // false
```

### 閉包
```js
function foo(data) {
    const getData = () => data
    const setData = n => data = n
    return {getData, setData}
}

const { getData, setData } = foo(10)

getData() //10
setData(50)
getData() //50
```

## DOM render 處理
-   建立渲染函式
-   建立共用組件
-   
### 建立渲染函式
```
export function renderFunction(bindDom, renderContent, contentData = []) {
  if (contentData.length) bindDom.innerHTML = updateElement([...contentData])

  function updateElement(newData) {
    contentData = newData
    bindDom.innerHTML = newData.map(renderContent).join('')
  }

  return updateElement
}
```