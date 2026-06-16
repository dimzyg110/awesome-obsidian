---
type: dashboard
tags: [dashboard]
---

# 👥 CRM Dashboard

## 🏭 Suppliers
```dataview
TABLE status AS "Status"
FROM #company AND -"Templates"
WHERE category = "supplier"
SORT file.name ASC
```

## 🛒 Clients
```dataview
TABLE status AS "Status"
FROM #company AND -"Templates"
WHERE category = "client"
SORT file.name ASC
```

## 👤 People
```dataview
TABLE company AS "Company", role AS "Role", email AS "Email"
FROM #person AND -"Templates"
SORT company ASC
```

## 📞 Open follow-ups from meetings
```dataview
TASK
FROM #meeting AND -"Templates"
WHERE !completed
GROUP BY file.link
```

## 🕗 Recently touched companies & people
```dataview
TABLE file.mtime AS "Modified"
FROM (#company OR #person) AND -"Templates"
SORT file.mtime DESC
LIMIT 10
```
