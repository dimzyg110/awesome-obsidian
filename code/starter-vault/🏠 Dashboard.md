---
type: dashboard
tags: [dashboard]
---

# 🏠 Dashboard

## 🔴 Overdue tasks
```dataview
TASK
FROM -"Templates"
WHERE !completed AND due AND due < date(today)
SORT due ASC
```

## 📌 Due today & undated open tasks
```dataview
TASK
FROM -"Templates"
WHERE !completed AND (due = date(today) OR !due)
GROUP BY file.link
```

## 📆 Upcoming (next 7 days)
```dataview
TASK
FROM -"Templates"
WHERE !completed AND due > date(today) AND due <= date(today) + dur(7 days)
SORT due ASC
```

## 🗂️ Active projects
```dataview
TABLE status AS "Status", file.mtime AS "Last touched"
FROM #project AND -"Templates"
WHERE status != "done"
SORT file.mtime DESC
```

## 🐌 Stale projects (no update in 14 days)
```dataview
TABLE status AS "Status", file.mtime AS "Last touched"
FROM #project AND -"Templates"
WHERE status != "done" AND file.mtime < date(today) - dur(14 days)
SORT file.mtime ASC
```

## 🤝 Recent meetings
```dataview
TABLE company AS "Company", project AS "Project", date AS "Date"
FROM #meeting AND -"Templates"
SORT date DESC
LIMIT 10
```

## 🕗 Recently edited notes
```dataview
TABLE file.mtime AS "Modified"
FROM -"Templates"
WHERE type != "daily" AND type != "dashboard"
SORT file.mtime DESC
LIMIT 10
```

## 📓 This week's daily notes
```dataview
LIST
FROM #daily AND -"Templates"
WHERE week = dateformat(date(today), "kkkk-'W'WW")
SORT date DESC
```
