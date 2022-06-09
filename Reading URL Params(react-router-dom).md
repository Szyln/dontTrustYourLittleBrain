---
title: "Reading URL Params(react-router-dom)"
tag: 
- 
---

##  Reading URL Params(react-router-dom)
>- [Routing for pattern 回應有規律的網址](Routing%20for%20pattern%20回應有規律的網址.md)

```jsx
{invoices.map((invoice) => (
	<Link
		to={`/invoices/${invoice.number}`}
		key={invoice.number}
	>
		{invoice.name}
	</Link>
))}
```

```jsx
<Route path="invoices" element={<Invoices />}>
	<Route path=":invoiceId" element={<Invoice />} />
</Route>
```