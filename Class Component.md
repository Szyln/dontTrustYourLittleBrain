## Class Component
```jsx
// 一定要繼承 React.Component 來寫，結果跟 function component 一樣
// 這裡面的 render 不等於 ReactDOM.render()
class Car extends React.Component {
  render() {
    return <h2>Hi, I am a Car!</h2>;
  }
}

// function component 寫法

function Car() {
  return <h2>Hi, I am a Car!</h2>;
}
```