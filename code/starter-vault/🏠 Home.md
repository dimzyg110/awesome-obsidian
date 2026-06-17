---
type: home
tags: [home]
---

# 🏠 Home

**Jump to:** [[🏠 Dashboard|Work]] · [[👥 CRM Dashboard|CRM]] · [[📦 Inventory Dashboard|Inventory]] · [[📊 Orders Dashboard|Orders]] · [[Projects Board|Kanban]]

## 📥 Inbox to triage
Capture anywhere with a `#inbox` task, or drop a note in the `Inbox/` folder.
```dataview
TASK
FROM -"Templates"
WHERE !completed AND contains(tags, "#inbox")
GROUP BY file.link
```
```dataview
LIST
FROM "Inbox" AND -"Templates"
SORT file.ctime DESC
```

## 🔻 Low stock
```dataview
TABLE quantity AS "On hand", reorder AS "Reorder at", location AS "Location"
FROM #inventory AND -"Templates"
WHERE quantity <= reorder
SORT quantity ASC
```

## 🛠️ SOPs due for review (next 14 days)
```dataview
TABLE owner AS "Owner", nextreview AS "Next review"
FROM #sop AND -"Templates"
WHERE nextreview AND nextreview <= date(today) + dur(14 days)
SORT nextreview ASC
```

## ⚖️ Open compliance actions
```dataview
TABLE area AS "Area", status AS "Status", deadline AS "Due", owner AS "Owner"
FROM #compliance AND -"Templates"
WHERE status != "closed"
SORT deadline ASC
```

## ⚠️ Open recalls
```dataview
TABLE severity AS "Severity", status AS "Status", owner AS "Owner"
FROM #recall AND -"Templates"
WHERE status != "closed"
SORT file.mtime DESC
```

## 📤 Open sales orders
```dataview
TABLE customer AS "Customer", status AS "Status", shipdate AS "Ship date"
FROM #so AND -"Templates"
WHERE status != "shipped" AND status != "closed"
SORT shipdate ASC
```

## ↩️ Open returns (RMA)
```dataview
TABLE customer AS "Customer", status AS "Status", reason AS "Reason"
FROM #rma AND -"Templates"
WHERE status != "closed" AND status != "refunded"
SORT file.mtime DESC
```

---

## 🗂️ Work dashboard
![[🏠 Dashboard]]

## 👥 CRM dashboard
![[👥 CRM Dashboard]]
