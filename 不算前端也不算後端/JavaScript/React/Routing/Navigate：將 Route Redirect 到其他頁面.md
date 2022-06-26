---
title: "Navigate：將 Route Redirect 到其他頁面"
tag: 
- js/react
- js/module/npm
- routing
---

##  Navigate：將 Route Redirect 到其他頁面

```jsx
import { BrowserRouter, Routes, Route, Navigate} from 'react-router-dom'

const App = () => {
	return (
	  <>
      <Nav />
      {/* 使用 Routes 包住 Route */}
      <Routes>
				{/* Route 決定點連結之後會產生的內容 */}
        <Route path="/" element={<HomePage />} />
        <Route path="/about" element={<About />} />
        <Route path="/aboutUs" element={<Navigate to="/about" replace />} />
      </Routes>
      <Footer />
    </>
	)
}
```