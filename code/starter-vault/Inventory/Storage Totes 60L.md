---
type: inventory
sku: TOTE-60L
category: Equipment
location: Aisle 1 / Bay A
quantity: 48
unit: each
reorder: 10
supplier: Example Co
updated: 2026-06-16
tags: [inventory]
---

# Storage Totes 60L

**SKU:** TOTE-60L
**Category:** Equipment
**Location:** Aisle 1 / Bay A
**On hand:** 48
**Reorder level:** 10
**Supplier:** [[Example Co]]

## 📝 Notes
Demo item (healthy stock).

## 🔁 Movement history
```dataview
TABLE direction AS "Dir", quantity AS "Qty", date AS "Date", reason AS "Reason"
FROM #movement AND -"Templates"
WHERE contains(string(item), this.file.name)
SORT date DESC
```
