# Key prop when Rendering List
> 使用 [[UUID]] 來生生成 key prop

撰寫 list 的時候，React 會因為沒有加上 key 這個唯一性的屬性而跳出警示
因為用其他非唯一性的屬性作為 event handler 的參考的話，很容易出現問題

```jsx
const deleteHandler = () => {
// 使用文字做基準的話，有兩個 li 都是相同內文的話就會一起刪掉
setMessage(message.filter(m => m !== msg))
}
```

#js #react #html 