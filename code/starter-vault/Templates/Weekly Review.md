---
date: <% tp.date.now("YYYY-MM-DD") %>
type: weekly
week: <% tp.date.now("GGGG-[W]WW") %>
tags: [weekly]
---

# Weekly Review — <% tp.date.now("GGGG-[W]WW") %>

Week of <% tp.date.now("MMMM Do", 1 - parseInt(tp.date.now("E"))) %> → <% tp.date.now("MMMM Do", 7 - parseInt(tp.date.now("E"))) %>

## 📆 This week's daily notes
```dataview
LIST
FROM #daily AND -"Templates"
WHERE week = this.week
SORT date ASC
```

## ✅ Completed this week
> Needs the **Tasks** plugin (or a `✅ YYYY-MM-DD` done-date) so completions carry a date.
```dataview
TASK
FROM -"Templates"
WHERE completed AND completion AND dateformat(completion, "kkkk-'W'WW") = this.week
GROUP BY file.link
```

## ⏳ Still open / carry over
```dataview
TASK
FROM -"Templates"
WHERE !completed AND due AND due <= this.file.day + dur(7 days)
SORT due ASC
```

## 🏆 Wins
- 

## 🪨 Challenges / blockers
- 

## 📚 What I learned
- 

## 🎯 Focus for next week
- [ ] 
