### filter()
回傳符合條件的所有元素
```js
let array = [1, 2, 4, 6];  
let newArray = array.filter(function(item){  
return item !== 6
});  
console.log(newArray);  
  
// [1,2,4]
```