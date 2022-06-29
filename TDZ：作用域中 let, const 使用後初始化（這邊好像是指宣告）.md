## TDZ：作用域中 let, const 使用後初始化（這邊好像是指宣告）
>[重複宣告一個外層的變數](重複宣告一個外層的變數.md)，並不是 TDZ 的因素，還是要該作用域中使用後宣告才會 TDZ

error: `can't access lexical declaration 'b' before initialization`
```js
// const b = 1 // OK
// let b       // undefined，OK
// var b       // undefined，OK 
console.log(b) 
// const b = 1 // TDZ 炸，宣告前使用 lexical declaration
// let b       // TDZ 炸，宣告前使用 lexical declaration
// var b       // undefined，不會炸，hoisting

```


### 作用域中有使用後宣告就會 TDZ
>[重複宣告一個外層的變數](重複宣告一個外層的變數.md)

![](重複宣告一個外層的變數.md#^18992d)