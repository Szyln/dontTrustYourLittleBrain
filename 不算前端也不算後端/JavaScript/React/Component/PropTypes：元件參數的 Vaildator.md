---
title: "PropTypes：元件參數的 Vaildator"
tag: 
- js/react/component 
- validators
- node/npm
- debug/lint
---
# PropTypes
>[PropTypes 的 lint 規則](PropTypes%20的%20lint%20規則.md)


React 在使用 [[Component：可重複利用、自定參數的元件]] 的時候，參數可以透過 `PropTypes` 來定義規範，避免每次使用元件時，造成非預期的結果

>- 必須安裝：prop-types（[npm](https://www.npmjs.com/package/prop-types )）
>- [更詳細的寫法參照 Usage](https://www.npmjs.com/package/prop-types)
>- 這功能會吃掉很多效能，開發期間可以使用 babel-plugin-transform-react-remove-prop-types 關掉：[npm](https://www.npmjs.com/package/babel-plugin-transform-react-remove-prop-types)

```jsx
import PropTypes from 'prop-types';
```
```jsx
function SayHello({firstName, lastName}) {
  return (
    <div>
      Hello {firstName} {lastName}!
    </div>
  )
}
// 定義 Vaildator
SayHello.propTypes = {
  firstName: PropTypes.string.isRequired,
  lastName: PropTypes.string.isRequired,
}
// log error
const element = <SayHello firstName={false} />
```

```jsx
// 常用的 PropTypes
// 要定義的參數名稱: PropTypes.<格式>
{
 optionalArray: PropTypes.array,
 optionalBool: PropTypes.bool,
 optionalFunc: PropTypes.func,
 optionalNumber: PropTypes.number,
 optionalObject: PropTypes.object,
 optionalString: PropTypes.string,
 optionalSymbol: PropTypes.symbol,
}
```



