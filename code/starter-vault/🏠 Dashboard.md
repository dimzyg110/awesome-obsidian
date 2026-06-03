---
type: dashboard
tags: [dashboard]
---

# 🏠 Dashboard

## 🔴 Overdue tasks
```dataview
TASK
WHERE !completed AND due AND due < date(today)
SORT due ASC
```

## 📌 Due today & undated open tasks
```dataview
TASK
WHERE !completed AND (due = date(today) OR !due)
GROUP BY file.link
```

## 📆 Upcoming (next 7 days)
```dataview
TASK
WHERE !completed AND due > date(today) AND due <= date(today) + dur(7 days)
SORT due ASC
```

## 🗂️ Active projects
```dataview
TABLE status AS "Status", file.mtime AS "Last touched"
FROM #project
WHERE status != "done"
SORT file.mtime DESC
```

## 🤝 Recent meetings
```dataview
TABLE company AS "Company", project AS "Project", date AS "Date"
FROM #meeting
SORT date DESC
LIMIT 10
```

## 🕗 Recently edited notes
```dataview
TABLE file.mtime AS "Modified"
WHERE type != "daily"
SORT file.mtime DESC
LIMIT 10
```

## 📓 This week's daily notes
```dataview
LIST
FROM #daily
WHERE week = dateformat(date(today), "kkkk-'W'WW")
SORT date DESC
```
