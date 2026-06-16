---
type: person
company: 
role: 
email: 
phone: 
tags: [person]
---

# <% tp.file.title %>

**Company:** 
**Role:** 
**Email:** 
**Phone:** 

## 📝 Notes
<% tp.file.cursor() %>

## 🔗 Mentions & meetings
Any note that links to this person with `[[<% tp.file.title %>]]` shows up here.
```dataview
LIST
FROM -"Templates"
WHERE contains(file.outlinks, this.file.link)
SORT file.mtime DESC
```
