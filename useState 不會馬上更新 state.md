---
title: "useState 不會馬上更新 state"
tag: 
- js/react/hook
---

##  useState 不會馬上更新 state
>[The useState set method is not reflecting a change immediately](https://stackoverflow.com/questions/54069253/the-usestate-set-method-is-not-reflecting-a-change-immediately)
>
>**state values are used by functions based on their current closures, and state updates will reflect in the next re-render by which the existing closures are not affected, but new ones are created**

- `useState` 是非同步語法
- state 的更新要等到 re-render 之後，先行的這個 closures 還不會作用
- 要馬上更新的話要使用 [useEffect Hook](useEffect%20Hook.md)


