---
type: moc
tags: [moc]
---

# 📇 Index — Map of Content

## 🧭 Dashboards
- [[🏠 Home]] — command center (embeds the work & CRM dashboards)
- [[🏠 Dashboard]] — tasks & projects
- [[👥 CRM Dashboard]] — people & companies
- [[📒 Directory]] — A–Z suppliers, clients & people
- [[📦 Inventory Dashboard]] — stock, POs, batches, movements
- [[📊 Orders Dashboard]] — POs, sales orders & returns by status
- [[📱 Mobile Home]] — lightweight phone view
- [[Projects Board]] — Kanban

## 📖 Reference
- [[📖 Vault Guide]] — how the whole system fits together
- [[✅ Getting Started]] — first-run checklist

## 📊 Records by type
```dataview
TABLE length(rows) AS "Count"
FROM -"Templates"
WHERE type
GROUP BY type AS "Type"
SORT length(rows) DESC
```

## 🕗 Recently edited
```dataview
TABLE type AS "Type", file.mtime AS "Modified"
FROM -"Templates"
WHERE type != "daily"
SORT file.mtime DESC
LIMIT 15
```
