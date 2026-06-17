---
type: dashboard
tags: [dashboard]
---

# 📊 Orders Dashboard

## 📥 Purchase orders by status
```dataview
TABLE length(rows) AS "Count", sum(rows.total) AS "Value"
FROM #po AND -"Templates"
GROUP BY status AS "Status"
```

## 📤 Sales orders by status
```dataview
TABLE length(rows) AS "Count", sum(rows.total) AS "Value"
FROM #so AND -"Templates"
GROUP BY status AS "Status"
```

## ↩️ Returns by status
```dataview
TABLE length(rows) AS "Count"
FROM #rma AND -"Templates"
GROUP BY status AS "Status"
```

---

## 🧾 Open purchase orders
```dataview
TABLE supplier AS "Supplier", status AS "Status", expected AS "Expected", total AS "Total"
FROM #po AND -"Templates"
WHERE status != "received"
SORT expected ASC
```

## 📤 Open sales orders
```dataview
TABLE customer AS "Customer", status AS "Status", shipdate AS "Ship date", total AS "Total"
FROM #so AND -"Templates"
WHERE status != "shipped" AND status != "closed"
SORT shipdate ASC
```

## ↩️ Open returns (RMA)
```dataview
TABLE customer AS "Customer", order AS "Order", status AS "Status", reason AS "Reason"
FROM #rma AND -"Templates"
WHERE status != "closed" AND status != "refunded"
SORT file.mtime DESC
```
