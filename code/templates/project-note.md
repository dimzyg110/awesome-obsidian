---
date: <% tp.date.now("YYYY-MM-DD") %>
type: project
status: active
company: 
target: 
tags: [project]
---

# <% tp.file.title %>

**Status:** active <%* /* active | on-hold | done */ %>
**Company / client:** 
**Started:** <% tp.date.now("YYYY-MM-DD") %>
**Target date:** 

## 🎯 Goal / outcome
<% tp.file.cursor() %>

## 📋 Tasks
- [ ] 

## 🤝 Related meetings
```dataview
TABLE date AS "Date", company AS "Company"
FROM #meeting AND -"Templates"
WHERE contains(string(project), this.file.name)
SORT date DESC
```

## 📝 Notes & decisions
- 

## 🔗 Resources
- 
