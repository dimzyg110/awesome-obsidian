---
type: po
supplier: 
status: draft
ordered: 
expected: 
received: 
total: 0
tags: [po]
---

# <% tp.file.title %>

**Supplier:** 
**Status:** draft <%* /* draft | ordered | received */ %>
**Ordered:** 
**Expected:** 
**Received:** 
**Total:** 

## 📦 Line items
| Item | Qty | Unit price | Line total |
| ---- | --- | ---------- | ---------- |
|  |  |  |  |

## 📝 Notes
<% tp.file.cursor() %>

## 🔗 Receiving
When stock arrives, update the matching items in `Inventory/` and set **Status** to `received`.
