---
type: company
category: supplier
status: active
tags: [company]
---

# <% tp.file.title %>

**Category:** supplier <%* /* supplier | client | partner */ %>
**Status:** active

## 📝 Notes
<% tp.file.cursor() %>

## 👥 People here
```dataview
TABLE role AS "Role", email AS "Email"
FROM #person AND -"Templates"
WHERE contains(string(company), this.file.name)
SORT role ASC
```

## 🤝 Meetings
```dataview
TABLE date AS "Date"
FROM #meeting AND -"Templates"
WHERE contains(string(company), this.file.name)
SORT date DESC
```

## 🗂️ Active projects
```dataview
TABLE status AS "Status"
FROM #project AND -"Templates"
WHERE contains(string(company), this.file.name) AND status != "done"
SORT file.mtime DESC
```
