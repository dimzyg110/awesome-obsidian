---
date: <% tp.date.now("YYYY-MM-DD") %>
type: rma
customer: 
order: 
status: requested
reason: 
tags: [rma]
---

# <% tp.file.title %>

**Date:** <% tp.date.now("YYYY-MM-DD") %>
**Customer:** 
**Sales order:** 
**Status:** requested <%* /* requested | approved | received | refunded | closed */ %>
**Reason:** 

## 📦 Items returned
- 

## 🛠️ Resolution
<% tp.file.cursor() %>

Link the original order with `[[SO-…]]` so this shows on that order.
