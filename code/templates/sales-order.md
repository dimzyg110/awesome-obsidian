---
type: so
customer: 
status: draft
ordered: <% tp.date.now("YYYY-MM-DD") %>
shipdate: 
total: 0
tags: [so]
---

# <% tp.file.title %>

**Customer:** 
**Status:** draft <%* /* draft | confirmed | picked | shipped | closed */ %>
**Ordered:** <% tp.date.now("YYYY-MM-DD") %>
**Ship date:** 
**Total:** 

## 📦 Line items
| Item | Qty | Unit price | Line total |
| ---- | --- | ---------- | ---------- |
|  |  |  |  |

## 📝 Notes
<% tp.file.cursor() %>

## ↩️ Returns referencing this order
```dataview
LIST
FROM #rma AND -"Templates"
WHERE contains(file.outlinks, this.file.link)
SORT file.mtime DESC
```
