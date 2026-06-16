---
type: dashboard
tags: [dashboard]
---

# 📦 Inventory Dashboard

## 🔻 Low stock — reorder now
```dataview
TABLE quantity AS "On hand", reorder AS "Reorder at", location AS "Location", supplier AS "Supplier"
FROM #inventory AND -"Templates"
WHERE quantity <= reorder
SORT quantity ASC
```

## 🧾 Open purchase orders
```dataview
TABLE supplier AS "Supplier", status AS "Status", expected AS "Expected", total AS "Total"
FROM #po AND -"Templates"
WHERE status != "received"
SORT expected ASC
```

## 📋 All stock by location
```dataview
TABLE quantity AS "On hand", reorder AS "Reorder at", sku AS "SKU"
FROM #inventory AND -"Templates"
SORT location ASC, file.name ASC
```

## 🕗 Recently updated items
```dataview
TABLE quantity AS "On hand", updated AS "Updated"
FROM #inventory AND -"Templates"
SORT updated DESC
LIMIT 10
```
