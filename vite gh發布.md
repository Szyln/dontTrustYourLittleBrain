https://dev.to/shashannkbawa/deploying-vite-app-to-github-pages-3ane

```shell
git init
git add .
git commit -m "first-commit"
git branch -M main
git remote add origin http://github.com/username/repo-name.git
git push -u origin main
```


```js
// vite.config.js
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'


// https://vitejs.dev/config/
export default defineConfig({
	base: '/slicing.DOYOGA/',		// 這裡寫入 repo 名稱
	plugins: [react()]
})
```

```shell
npm run build
```

```shell
git add dist -f
```

```shell
git commit -m "Adding dist"
```

```shell
git subtree push --prefix dist origin gh-pages
```