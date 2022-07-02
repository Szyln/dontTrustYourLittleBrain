## Function Factories
>[閉包 Closure](閉包%20Closure.md)
製造 function 的 function

```js
function makeAddress(nation) {
  return function (city, road) {
    if (nation === 'taiwan') {
      console.log(`${nation} ${city} city ${road} road`)
    }
    if (nation === 'japan') {
      console.log(`${nation} ${city} city ${road} road`);
      
    }
  }
}

// 每次執行函式都是新的 Function Execution Context
const taiwanAddress = makeAddress('taiwan')
const japanAddress = makeAddress('japan')
// 每次的 Closure 都是讀到不同個 Function Execution Context
// 所以不會讀到同一個記憶體上的 nation
taiwanAddress('taipei', 'bla')
taiwanAddress('tokyo', 'bla')
```