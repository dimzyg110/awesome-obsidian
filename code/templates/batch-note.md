---
type: batch
batchid: 
sku: 
product: 
supplier: 
quantity: 0
received: <% tp.date.now("YYYY-MM-DD") %>
expiry: 
status: quarantine
coa: 
tags: [batch]
---

# <% tp.file.title %>

**Batch ID:** 
**Product / SKU:** 
**Supplier:** 
**Quantity:** 0
**Received:** <% tp.date.now("YYYY-MM-DD") %>
**Expiry:** 
**Status:** quarantine <%* /* quarantine | released | recalled */ %>
**COA:** 

## 📝 Notes
<% tp.file.cursor() %>
