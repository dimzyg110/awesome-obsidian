---
type: meta
tags: [meta]
---

# 📖 Vault Guide

A small business operating system in Obsidian: capture → tasks → projects → CRM → inventory → procurement → fulfilment → returns, with traceability, compliance and reporting on top.

## Daily rhythm
1. Morning: open the **daily note** (calendar ribbon). Set 🎯 focus, add `- [ ]` tasks (use `📅 2026-06-20` for due dates).
2. Through the day: make **meeting**, **project**, **PO**, **SO**, **batch**, **movement** notes from Templater.
3. Triage **📥 Inbox** items.
4. End of day: fill the daily note's 🌙 review.
5. Friday: a **weekly review**; monthly: a **monthly review** and an **ops report**.

## Note types
| Type | Tag | Folder | Purpose |
| --- | --- | --- | --- |
| Daily | `#daily` | Journal/Daily | Journal + tasks |
| Weekly / Monthly | `#weekly` / `#monthly` | Journal | Reviews |
| Ops report | `#opsreport` | (anywhere) | Weekly leadership snapshot |
| Meeting | `#meeting` | Meetings | Attendees, decisions, actions |
| Project | `#project` | Projects | `status` + `target` date |
| Person / Company | `#person` / `#company` | People / Companies | CRM; company `category` = supplier/client/partner |
| Reference | `#reference` | References | Web clips / research |
| SOP | `#sop` | SOPs | Procedures + review dates |
| Inventory | `#inventory` | Inventory | Stock with `quantity` / `reorder` |
| Movement | `#movement` | Movements | in/out/adjust, linked to an item |
| Batch | `#batch` | Batches | Lot traceability + expiry + status |
| Recall | `#recall` | Recalls | Links affected `[[BATCH-…]]` |
| Purchase order | `#po` | Purchase Orders | Linked to a supplier |
| Sales order | `#so` | Sales Orders | Linked to a customer |
| Return / RMA | `#rma` | Returns | Linked to a `[[SO-…]]` |
| Compliance | `#compliance` | Compliance | Audit entries + corrective action |

## Conventions
- **Linking:** set a note's `company:`/`customer:`/`supplier:` field to the **exact company note name**, and use `[[wikilinks]]` for batches, orders and people so reverse-lookups work.
- **Status values:** project `active/on-hold/done`; PO `draft/ordered/received`; SO `draft/confirmed/picked/shipped/closed`; RMA `requested/approved/received/refunded/closed`; batch `quarantine/released/recalled`; compliance `open/in-progress/closed`.
- **Reserved fields:** Dataview tasks inherit page frontmatter, so notes use `target`/`deadline` (not `due`) for page-level dates; only `- [ ]` tasks carry `📅` due dates.
- **Meta/** notes (this guide, the setup checklist) are excluded from the task dashboards.

## Dashboards
- **🏠 Home** — command center (embeds Work + CRM, plus inbox, low stock, SOPs, compliance, recalls, orders, returns)
- **🏠 Dashboard** — tasks & projects · **👥 CRM** — people & companies
- **📦 Inventory** — stock, POs, batches, movements, fulfilment
- **📊 Orders** — POs / SOs / returns by status (count + value)
- **📱 Mobile Home** — lightweight phone view · **📇 Index** — map of content

## Workflows
- **Procure:** PO (supplier) → receive → set `received` (drives the supplier on-time scorecard) → create Batch + Movement (in).
- **Sell:** SO (customer) → pick/ship → Movement (out). Open SOs show on Home & Inventory.
- **Return:** RMA linked to its SO → resolve. Open RMAs show on Home.
- **Problem:** Recall links affected batches; pair with a Compliance entry for the corrective action.
