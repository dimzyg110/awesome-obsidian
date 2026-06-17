---
type: person
company: Example Co
role: Buyer
email: jane@example.com
phone: 
tags: [person]
---

# Jane Doe

**Company:** [[Example Co]]
**Role:** Buyer
**Email:** jane@example.com
**Phone:** 

## 📝 Notes
Demo contact — delete once you add real people.

## 🔗 Mentions & meetings
```dataview
LIST
FROM -"Templates"
WHERE contains(file.outlinks, this.file.link)
SORT file.mtime DESC
```
