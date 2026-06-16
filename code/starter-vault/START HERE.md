# 👋 START HERE

This is a ready-to-run vault for a daily-journal + task + project workflow.

## 1. Open it
In Obsidian: **Open folder as vault** → select this `code/starter-vault` folder from the repo (or copy it out and rename it to whatever you like first).

## 2. Install 3 community plugins
**Settings → Community plugins → Turn on community plugins → Browse**, then install + enable:
- **Templater**
- **Dataview**
- **Tasks** (optional but recommended for due dates)

Also enable the core **Daily Notes** plugin (Settings → Core plugins).

## 3. Point the plugins at the folders
- **Templater** → *Template folder location* = `Templates`. Turn ON *Trigger Templater on new file creation*.
- **Daily Notes** → *Template file location* = `Templates/Daily Note`; *New file location* = `Journal/Daily`.
- **Dataview** → no extra settings needed (all blocks use plain DQL; leave *JavaScript Queries* OFF).

## 4. Use it
- Press the **Daily Note** ribbon icon (calendar) each morning → today's journal is created from the template.
- New meeting → **Templater: create new note from template → Meeting Note**, save into `Meetings/`.
- New project → same, **Project Note** → `Projects/`.
- Open **🏠 Dashboard** and pin it — it pulls tasks, projects and meetings from everywhere.

The `Example Project` and example meeting are just demo data so the dashboard isn't empty — delete them once you're rolling.

## Styling (already on)
Five CSS snippets ship pre-enabled in `.obsidian/snippets/`: nicer (round) checkboxes, tag pills, stylish blockquotes, a slimmer scrollbar and an auto-fading UI. Toggle any of them in **Settings → Appearance → CSS snippets**.

For the **Projects Board** (Kanban), also install the **Kanban** community plugin.

## Folders
```
Templates/             the note templates
Journal/Daily/         daily notes land here
Journal/Weekly/        weekly reviews
Meetings/              meeting notes
Projects/              one note per project (#project + status:)
Companies/             suppliers / clients / partners (#company)
People/                contacts (#person)
References/            web clips & research (#reference)
SOPs/                  standard operating procedures (#sop)
Inventory/             stock items (#inventory)
Purchase Orders/       POs linked to suppliers (#po)
Batches/               lot / batch traceability (#batch)
Recalls/               recalls linked to batches (#recall)
Movements/             stock in/out/adjust log (#movement)
Sales Orders/          outbound orders (#so)
Returns/               returns / RMAs (#rma)
Compliance/            audit / compliance log (#compliance)
Inbox/                 quick capture, triaged from Home
Meta/                  setup checklist (excluded from dashboards)
📇 Index.md            map of content (all dashboards & record types)
🏠 Home.md             command center (embeds the dashboards)
🏠 Dashboard.md        work dashboard
👥 CRM Dashboard.md    people & companies
📦 Inventory Dashboard.md  low stock, POs & by location
📊 Orders Dashboard.md  POs, sales orders & returns by status
📱 Mobile Home.md      lightweight phone view
Projects Board.md      Kanban board (needs the Kanban plugin)
```
