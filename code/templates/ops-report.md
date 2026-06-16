---
date: <% tp.date.now("YYYY-MM-DD") %>
type: opsreport
week: <% tp.date.now("GGGG-[W]WW") %>
tags: [opsreport]
---

# Ops Report — <% tp.date.now("GGGG-[W]WW") %>

## 🔻 Stock to reorder
```dataview
TABLE quantity AS "On hand", reorder AS "Reorder at", supplier AS "Supplier"
FROM #inventory AND -"Templates"
WHERE quantity <= reorder
SORT quantity ASC
```

## 🧾 Open purchase orders
```dataview
TABLE supplier AS "Supplier", status AS "Status", expected AS "Expected"
FROM #po AND -"Templates"
WHERE status != "received"
SORT expected ASC
```

## ⚖️ Open compliance actions
```dataview
TABLE area AS "Area", status AS "Status", deadline AS "Due"
FROM #compliance AND -"Templates"
WHERE status != "closed"
SORT deadline ASC
```

## 🧬 Batches expiring (next 30 days)
```dataview
TABLE product AS "Product", expiry AS "Expiry", status AS "Status"
FROM #batch AND -"Templates"
WHERE expiry AND expiry <= date(today) + dur(30 days) AND status != "recalled"
SORT expiry ASC
```

## 🗂️ Active projects
```dataview
TABLE status AS "Status"
FROM #project AND -"Templates"
WHERE status != "done"
SORT file.mtime DESC
```

## 📝 Summary for leadership
- **Highlights:**
- **Risks:**
- **Decisions needed:**
