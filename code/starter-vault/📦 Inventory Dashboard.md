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

## 🧬 Batches expiring soon (next 30 days)
```dataview
TABLE product AS "Product", quantity AS "Qty", expiry AS "Expiry", status AS "Status"
FROM #batch AND -"Templates"
WHERE expiry AND expiry <= date(today) + dur(30 days) AND status != "recalled"
SORT expiry ASC
```

## 🚧 Batches in quarantine
```dataview
TABLE product AS "Product", quantity AS "Qty", received AS "Received"
FROM #batch AND -"Templates"
WHERE status = "quarantine"
SORT received ASC
```

## 🔁 Recent stock movements
```dataview
TABLE item AS "Item", direction AS "Dir", quantity AS "Qty", reason AS "Reason"
FROM #movement AND -"Templates"
SORT date DESC
LIMIT 15
```

## 📤 Open sales orders (to fulfil)
```dataview
TABLE customer AS "Customer", status AS "Status", shipdate AS "Ship date", total AS "Total"
FROM #so AND -"Templates"
WHERE status != "shipped" AND status != "closed"
SORT shipdate ASC
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
