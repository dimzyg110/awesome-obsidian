---
date: <% tp.date.now("YYYY-MM-DD") %>
type: recall
status: open
severity: 
owner: 
tags: [recall]
---

# <% tp.file.title %>

**Date initiated:** <% tp.date.now("YYYY-MM-DD") %>
**Status:** open <%* /* open | contained | closed */ %>
**Severity:** 
**Owner:** 

## ⚠️ Reason
<% tp.file.cursor() %>

## 📦 Affected batches
Link each affected lot with `[[BATCH-…]]` so it cross-references on the batch page:
- 

## 🛠️ Actions
- [ ] Quarantine affected stock
- [ ] Notify affected customers
- [ ] File compliance report

## 🔗 Related compliance
- 
