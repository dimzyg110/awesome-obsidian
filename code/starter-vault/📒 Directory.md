---
type: dashboard
tags: [dashboard]
---

# 📒 Directory

## 🏭 Suppliers
```dataview
LIST
FROM #company AND -"Templates"
WHERE category = "supplier"
SORT file.name ASC
```

## 🛒 Clients
```dataview
LIST
FROM #company AND -"Templates"
WHERE category = "client"
SORT file.name ASC
```

## 👤 People
```dataview
TABLE company AS "Company", role AS "Role", email AS "Email", phone AS "Phone"
FROM #person AND -"Templates"
SORT file.name ASC
```
