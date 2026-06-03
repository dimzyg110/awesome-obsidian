---
date: <% tp.date.now("YYYY-MM-DD") %>
type: weekly
week: <% tp.date.now("GGGG-[W]WW") %>
tags: [weekly]
---

# Weekly Review — <% tp.date.now("GGGG-[W]WW") %>

Week of <% tp.date.now("MMMM Do") %> → <% tp.date.now("MMMM Do", 6) %>

## 📆 This week's daily notes
```dataview
LIST
FROM #daily
WHERE week = this.week
SORT date ASC
```

## ✅ Completed this week
```dataview
TASK
WHERE completed AND completion >= this.file.day - dur(6 days) AND completion <= this.file.day
GROUP BY file.link
```

## ⏳ Still open / carry over
```dataview
TASK
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
