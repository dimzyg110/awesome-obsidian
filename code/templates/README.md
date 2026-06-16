# Note templates

Ready-to-use [Templater](https://github.com/SilentVoid13/Templater) templates for a daily-journal + task workflow. They pair with the Dataview dashboard in [`../dashboards/dashboard.md`](../dashboards/dashboard.md).

## Setup

1. Install the **Templater** and **Dataview** community plugins. Enable the core **Daily Notes** plugin.
2. Copy these `.md` files into a `Templates/` folder in your vault.
3. **Templater settings** → set *Template folder location* to `Templates`. Enable *Trigger Templater on new file creation*.
4. **Daily Notes settings** → set *Template file location* to `Templates/daily-note` and choose where new daily notes are stored (e.g. `Journal/Daily`).

All dashboard and template blocks use plain Dataview **DQL** (no `dataviewjs`), so you do **not** need to enable *JavaScript Queries* — leaving it off keeps the vault safer.

## Templates

| File | Trigger / tag | What it does |
| --- | --- | --- |
| [`daily-note.md`](daily-note.md) | `#daily` | Dated journal with auto yesterday/tomorrow links, focus, tasks, meetings and an end-of-day review. |
| [`meeting-note.md`](meeting-note.md) | `#meeting` | Structured meeting note with attendees, decisions and action items (tasks). |
| [`weekly-review.md`](weekly-review.md) | `#weekly` | Rolls up the week's daily notes, completed tasks and open items for a review. |
| [`project-note.md`](project-note.md) | `#project` | One note per project with a `status:` field; populates the dashboard's *Active projects* view and lists its related meetings. |
| [`monthly-review.md`](monthly-review.md) | `#monthly` | Month-level roll-up of daily notes, completed tasks and projects touched. |
| [`person-note.md`](person-note.md) | `#person` | A contact (client/supplier staff) with company, role and links to every note that mentions them. |
| [`company-note.md`](company-note.md) | `#company` | A supplier/client/partner account; auto-lists its people, meetings and active projects. |
| [`reference-note.md`](reference-note.md) | `#reference` | A web-clip / research note with source and key points. |
| [`sop-note.md`](sop-note.md) | `#sop` | A standard operating procedure with owner, status and review dates. |
| [`inventory-item.md`](inventory-item.md) | `#inventory` | A stock item with SKU, location, quantity, reorder level and supplier. |
| [`purchase-order.md`](purchase-order.md) | `#po` | A purchase order linked to a supplier; open POs surface on the inventory dashboard. |
| [`compliance-log.md`](compliance-log.md) | `#compliance` | A compliance/audit entry with area, owner, due date and corrective action. |
| [`batch-note.md`](batch-note.md) | `#batch` | A lot/batch with expiry and quarantine/released/recalled status for traceability. |
| [`ops-report.md`](ops-report.md) | `#opsreport` | A weekly leadership snapshot: reorders, open POs, compliance, expiring batches, projects. |
| [`recall-note.md`](recall-note.md) | `#recall` | A recall that links affected `[[BATCH-…]]` lots; open recalls surface on Home, and each batch lists the recalls referencing it. |
| [`stock-movement.md`](stock-movement.md) | `#movement` | An in/out/adjust stock movement linked to an item; feeds the item's movement history and the inventory dashboard. |

Company (supplier) notes include an on-time delivery scorecard driven by each PO's `expected` vs `received` date.

Dashboards live in [`../dashboards/`](../dashboards): the work dashboard, [`crm-dashboard.md`](../dashboards/crm-dashboard.md), [`inventory-dashboard.md`](../dashboards/inventory-dashboard.md) (low-stock / by-location) and [`home.md`](../dashboards/home.md) — a command-center that embeds the others plus an inbox-triage and SOP-review view. A Kanban board lives in [`../boards/projects-board.md`](../boards/projects-board.md) (needs the **Kanban** community plugin). There's also a lightweight [`mobile-home.md`](../dashboards/mobile-home.md) for phones (no embedded dashboards).

The CRM templates (`person`, `company`) pair with a second dashboard, [`../dashboards/crm-dashboard.md`](../dashboards/crm-dashboard.md). Link records together by setting a meeting/project/person's `company:` field to the **exact file name** of the company note, and by mentioning people with `[[Their Name]]`.

## How it fits together

- Every `- [ ]` task in any note is surfaced by the dashboard, sorted by due date.
- Tag project notes with `#project` and a `status:` field to populate the **Active projects** view.
- The `week:` frontmatter (ISO week, e.g. `2026-W23`) links daily notes to their weekly review.

Add due dates and priority to tasks with Tasks-plugin syntax, e.g. `- [ ] Call supplier 📅 2026-06-10 🔼`.

## Troubleshooting

- **Template files showing up as real notes/tasks.** The templates carry tags (`#daily`, `#meeting`, `#project`) and empty `- [ ]` lines, so Dataview will index them unless excluded. All queries here use `FROM -"Templates"` to scope them out — keep your templates in a folder named `Templates`. As a belt-and-suspenders measure, also add `Templates` under **Dataview settings → Exclude folders**.
- **"Completed this week" is empty.** That query filters by completion *date*, which only exists when a task is marked done with a `✅ YYYY-MM-DD` stamp. Install the **Tasks** plugin (it adds the done-date automatically) or add the stamp by hand.
- **Daily note shows raw `<% ... %>` text.** Templater isn't firing on creation — enable *Trigger Templater on new file creation*, and point Daily Notes at the same template file.
- **Daily note for a past/future date shows the wrong day.** The daily template anchors its dates to the note title, so keep the Daily Notes date format at `YYYY-MM-DD` (the default) — that's the format the template parses the title with.
- **Dashboard blocks blank.** Make sure the **Dataview** plugin is enabled, then reload Obsidian (`Ctrl/Cmd+R`) so it indexes the vault.
