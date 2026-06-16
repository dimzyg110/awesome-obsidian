---
type: home
tags: [home, mobile]
---

# 📱 Mobile Home

A lightweight, phone-friendly view (no embedded dashboards). Pin it on mobile.

**Capture:** [[📥 Inbox]] · **Boards:** [[Projects Board]]

## 📌 Due today & overdue
```dataview
TASK
FROM -"Templates"
WHERE !completed AND due AND due <= date(today)
SORT due ASC
```

## 📥 Inbox
```dataview
TASK
FROM -"Templates"
WHERE !completed AND contains(tags, "#inbox")
```

## 🔻 Low stock
```dataview
TABLE quantity AS "On hand", reorder AS "Reorder at"
FROM #inventory AND -"Templates"
WHERE quantity <= reorder
SORT quantity ASC
```

## ⚖️ Open compliance actions
```dataview
TABLE status AS "Status", deadline AS "Due"
FROM #compliance AND -"Templates"
WHERE status != "closed"
SORT deadline ASC
```
