---
date: <% tp.date.now("YYYY-MM-DD") %>
type: monthly
month: <% tp.date.now("YYYY-MM") %>
tags: [monthly]
---

# Monthly Review — <% tp.date.now("MMMM YYYY") %>

## 📆 Daily notes this month
```dataview
LIST
FROM #daily AND -"Templates"
WHERE dateformat(file.day, "yyyy-MM") = this.month
SORT file.day ASC
```

## ✅ Completed this month
> Needs the **Tasks** plugin (or a `✅ YYYY-MM-DD` done-date) so completions carry a date.
```dataview
TASK
FROM -"Templates"
WHERE completed AND completion AND dateformat(completion, "yyyy-MM") = this.month
GROUP BY file.link
```

## 🗂️ Projects touched this month
```dataview
TABLE status AS "Status", file.mtime AS "Last touched"
FROM #project AND -"Templates"
WHERE dateformat(file.mtime, "yyyy-MM") = this.month
SORT file.mtime DESC
```

## 🏆 Wins
- 

## 🪨 Challenges
- 

## 📚 Learnings
- 

## 🎯 Focus for next month
- [ ] 
