---
type: company
category: client
status: active
tags: [company]
---

# Bright Dispensary

**Category:** client
**Status:** active

## 📝 Notes
Demo client (so the CRM dashboard's Clients section and the outbound views populate). Delete once real.

## 👥 People here
```dataview
TABLE role AS "Role", email AS "Email"
FROM #person AND -"Templates"
WHERE contains(string(company), this.file.name)
SORT role ASC
```

## 🤝 Meetings
```dataview
TABLE date AS "Date"
FROM #meeting AND -"Templates"
WHERE contains(string(company), this.file.name)
SORT date DESC
```

## 🗂️ Active projects
```dataview
TABLE status AS "Status"
FROM #project AND -"Templates"
WHERE contains(string(company), this.file.name) AND status != "done"
SORT file.mtime DESC
```

## 🧾 Purchase orders & on-time delivery
```dataview
TABLE status AS "Status", expected AS "Expected", received AS "Received",
  choice(received AND received <= expected, "✅ on time", choice(received, "⚠️ late", "—")) AS "On time?"
FROM #po AND -"Templates"
WHERE contains(string(supplier), this.file.name)
SORT expected DESC
```

## 📤 Sales orders
```dataview
TABLE status AS "Status", ordered AS "Ordered", shipdate AS "Ship date", total AS "Total"
FROM #so AND -"Templates"
WHERE contains(string(customer), this.file.name)
SORT ordered DESC
```
