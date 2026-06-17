---
type: inventory
sku: 
category: 
location: 
quantity: 0
unit: 
reorder: 0
supplier: 
updated: <% tp.date.now("YYYY-MM-DD") %>
tags: [inventory]
---

# <% tp.file.title %>

**SKU:** 
**Category:** 
**Location:** 
**On hand:** 0
**Reorder level:** 0
**Supplier:** 

## 📝 Notes
<% tp.file.cursor() %>

## 🔁 Movement history
```dataview
TABLE direction AS "Dir", quantity AS "Qty", date AS "Date", reason AS "Reason"
FROM #movement AND -"Templates"
WHERE contains(string(item), this.file.name)
SORT date DESC
```
