---
title: "DOM 簡要"
aliases: Document Object Model,
tag: 
- js/dom
---
# DOM
> [DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
- Document Object Model
- 類似 [Object](Object.md)

## 節點 node
在 document 裡的物件們
-   element node
-   text node
-   attribute node

## 選取

### 選取節點
| 選取節點  | 單一選取                                             | 全部選取                                |
| --------- | ---------------------------------------------------- | --------------------------------------- |
| 語法      | `document.querySelector('selector')`（第一個符合的） | `document.querySelectorAll('selector')` |
| node 節點 | 一個 node                                            | nodelist（類陣列）                      |

### 選取內容｜內容、文字
| 選取內容物 | 內容（可以有其他節點） | 文字（沒有其他結顛） |
| ---------- | ---------------------- | -------------------- |
| node 節點  | {某節點}.innerHTML     | {某節點}.textContent |

### 選取屬性
```js
{某節點}.getAttribute(’{欲取得屬性}’)
```

## 新增與修改
### 新增、修改內容（包含節點）
```js
main.innerHTML = `<a href="${link}" class="header">超連結</a>;`
```
-   可搭配 Template Literals （`字串 ${變數}`） 來寫
-   若該節點本來裡面就有內容，則會被清除
### 新增、修改內容（不包含節點）
```js
{某節點}.textContent = {欲修改或新增的內容};
```
### 新增、修改屬性
```js
// setAttribute(屬性的名稱, 值)
document.querySelector(’a’).setAttribute(’href’, ’#’ );
```
## 查節點的名稱名
```js
// 只知道他的 js 的名稱，不知道他在 html 叫什麼
{ 某 selector }.nodeName
```

##  querySelector
-   querySelector｜一個節點
-   querySelectorAll｜一個類陣列
```js
// 有地蓋房子

  

// 在 document 上找地(section) 
const section = document.querySelector('section');
  

	 // 在 document 上生材料
	 const para = document.createElement('p');
	 para.textContent = 'hello world';

	 // 把生好的材料放上地(section)
	 section.appendChild(para);
 
```
## createElement()
```js
// 沒地蓋房子


// 先在 document 上生地
const section = document.createElement('section');

  

// 把地放上 document 上的 body
**document****.****body****.**appendChild(section);

  
// 在 document 上生材料
const para = document.createElement('p');
para.textContent = 'hello world';

  

// 把生好的材料放上地(section，不用從document開始寫)
**section****.**appendChild(para);
```


## 範圍取值
-   用 class 取比較不會撞到

## 自訂標籤屬性｜data-{自訂名稱}=”自訂內容”

  
