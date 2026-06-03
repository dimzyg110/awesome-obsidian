# Note templates

Ready-to-use [Templater](https://github.com/SilentVoid13/Templater) templates for a daily-journal + task workflow. They pair with the Dataview dashboard in [`../dashboards/dashboard.md`](../dashboards/dashboard.md).

## Setup

1. Install the **Templater** and **Dataview** community plugins. Enable the core **Daily Notes** plugin.
2. Copy these `.md` files into a `Templates/` folder in your vault.
3. **Templater settings** → set *Template folder location* to `Templates`. Enable *Trigger Templater on new file creation*.
4. **Daily Notes settings** → set *Template file location* to `Templates/daily-note` and choose where new daily notes are stored (e.g. `Journal/Daily`).
5. **Dataview settings** → enable *JavaScript Queries* (used by some dashboard blocks).

## Templates

| File | Trigger / tag | What it does |
| --- | --- | --- |
| [`daily-note.md`](daily-note.md) | `#daily` | Dated journal with auto yesterday/tomorrow links, focus, tasks, meetings and an end-of-day review. |
| [`meeting-note.md`](meeting-note.md) | `#meeting` | Structured meeting note with attendees, decisions and action items (tasks). |
| [`weekly-review.md`](weekly-review.md) | `#weekly` | Rolls up the week's daily notes, completed tasks and open items for a review. |
| [`project-note.md`](project-note.md) | `#project` | One note per project with a `status:` field; populates the dashboard's *Active projects* view and lists its related meetings. |

## How it fits together

- Every `- [ ]` task in any note is surfaced by the dashboard, sorted by due date.
- Tag project notes with `#project` and a `status:` field to populate the **Active projects** view.
- The `week:` frontmatter (ISO week, e.g. `2026-W23`) links daily notes to their weekly review.

Add due dates and priority to tasks with Tasks-plugin syntax, e.g. `- [ ] Call supplier 📅 2026-06-10 🔼`.
