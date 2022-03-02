## JSX HTML 內使用 if (Conditional (ternary) operator)
在 JSX 內可以寫 JS，但是有限制的，必須寫表現式
```jsx
function CharacterCount({text}) {
  return (
    <div>
    {/* if 必須要用表現式 Conditional (ternary) operator */}
      The text "{text}" has {text.length ? <strong>{text.length}</strong> : 'No'} characters
    </div>
  )
}
```

#js/react/jsx #js/logic