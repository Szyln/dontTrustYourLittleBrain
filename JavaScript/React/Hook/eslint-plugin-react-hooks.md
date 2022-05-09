---
title: "eslint-plugin-react-hooks"
tag: 
- js/react/hook
- node/npm
---
>[npm](https://www.npmjs.com/package/eslint-plugin-react-hooks)

撰寫 [[Hook]] 時的偵錯工具模組，[ESLint](JavaScript/Debug/ESLint.md) 安裝時會自動安裝，可以把下面的設定加上去
```shell
npm i eslint-plugin-react-hooks
```
## [ESLint](JavaScript/Debug/ESLint.md) 設定
記得要先設定 [ESLint](JavaScript/Debug/ESLint.md)
```js
// eslintrt.js
module.exports = {
  env: {
    browser: true,
    es2021: true,
  },
  extends: [
    'plugin:react/recommended',
    'airbnb',
+   'plugin:react-hooks/recommended', // 加入這個
  ],
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 'latest',
    sourceType: 'module',
  },
  plugins: ['react'],
  rules: {
+		'react-hooks/rules-of-hooks': 'error', // 加入這個
+   'react-hooks/exhaustive-deps': 'warn', // 加入這個
  },
};

```

#js/react/hook #node/npm