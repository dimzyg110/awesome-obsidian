---
type: project
status: active
company: Example Co
due: 2026-06-30
tags: [project]
---

# Example Project

**Status:** active
**Company / client:** Example Co
**Started:** 2026-06-03
**Target date:** 2026-06-30

## 🎯 Goal / outcome
Delete this note once you've created your first real project — it's here so the dashboard's *Active projects* view shows something on first open.

## 📋 Tasks
- [ ] First sample task 📅 2026-06-10
- [x] A finished task

## 🤝 Related meetings
```dataview
TABLE date AS "Date", company AS "Company"
FROM #meeting
WHERE contains(string(project), this.file.name)
SORT date DESC
```

## 📝 Notes & decisions
- 

## 🔗 Resources
- 
