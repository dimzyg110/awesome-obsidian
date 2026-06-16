---
date: <% tp.date.now("YYYY-MM-DD") %>
type: movement
item: 
direction: out
quantity: 0
reason: 
ref: 
tags: [movement]
---

# <% tp.file.title %>

**Date:** <% tp.date.now("YYYY-MM-DD") %>
**Item:** 
**Direction:** out <%* /* in | out | adjust */ %>
**Quantity:** 0
**Reason:** 
**Reference:** 

## 📝 Notes
<% tp.file.cursor() %>

Link the affected stock item with `[[Item name]]` so this shows in its movement history.
