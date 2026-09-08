---
tags:
  - TopLevel
  - HUB
banner: photo-1779089043065-599a0705d0da.jpg
cssclasses:
  - cards
---
# template-vault-general

A template vault for Obsidian made with general-purpose SW DEV notetaking in mind.

> ## Vault setup
> 
> Clone this, rename the vault folder and repo to your preferred name (e.g. `dev-vault`, `work-vault`, or `<company>-vault`), then customize with your own projects and notes.
> 
> 1. Rename the root vault folder and GitHub repository to match your workspace.
> 2. Enable community plugins in **Settings --> Community plugins**.
> 3. In **Settings --> `Dataview`**, enable both **Enable JavaScript Queries** and **Enable Inline JavaScript Queries**.
> 4. In **Settings --> `GitHub Sync`**, update the HTTPS clone address to your repository URL.
> 5. Create project folders at the vault root (see `Sample Project/` for an example), create a `<Name> - HUB.md` note using the `Project Hub` or `App Hub` template, and bookmark it for quick access.
> 6. See [[Templates - HUB]] for note templates and [[Examples]] for markdown, diagram, and `Dataview` syntax.

> [!INFO] Centralized task tracking
> - See [[Tasks]] for a unified view of all open checkboxes marked with `#todo`, `#review`, or `#suggestion` across the entire vault.
> - Check the box in any note or within `Tasks.md` to automatically resolve and update both.

> [!IMPORTANT] Plugins & CSS
> If cards, badges, or code formatting look unexpected, make sure community plugins and CSS snippets are enabled:
> - **Community Plugins:** `Colored Tags Wrangler`, `Contribution Graph`, `Dataview`, `GitHub Sync`, `Homepage`, `Mermaid Zoom`, `Mononote`, `Pretty Properties`, `Shiki Highlighter`, `Style Settings`, `Tasks`
> - **Custom CSS:** `callout-padding`, `cards`, `links`, `main-view`, `mermaid`, `mermaid-zoom`, `tasks`, `text-size`

## Status tags

Each child or issue note uses status tags to indicate state and surface in card grids:

| Tag      | Meaning                                     |
| -------- | ------------------------------------------- |
| #open    | Active task, open issue, or ongoing work.   |
| #closed  | Finished, resolved, or reviewed.            |
| #todo    | Yet to be started (used in notes or tasks). |
| #review  | Awaits human or peer review.                |
| #skipped | Deliberately deferred or dropped.           |

> [!NOTE] Task tags
> Checkboxes can also carry `#todo`, `#review`, or `#suggestion` (e.g., `- [ ] #todo refactor parser`). 
> These are automatically aggregated in [[Tasks]].

---

## Hubs

Each HUB file in the vault has its own folder and a bookmark for quick navigation.
```dataview
TABLE WITHOUT ID 
	file.link AS "Note"
FROM ""
WHERE contains(file.name, "HUB")
SORT file.name ASC
```

## Recent notes

12 most recently edited notes.
```dataview
TABLE WITHOUT ID
	file.link AS "Note",
	choice(file.folder, file.folder, "") AS "Parent",
	dateformat(file.mtime, "yyyy-MM-dd HH:mm") AS "Last Edited"
FROM ""
WHERE file.name != "Dashboard"
SORT file.mtime DESC
LIMIT 12
```

## Activity

Activity over the last 180 days.

```contributionGraph
graphType: default
dateRangeValue: 180
dateRangeType: LATEST_DAYS
startOfWeek: 0
showCellRuleIndicators: false
titleStyle:
  textAlign: left
  fontSize: 20px
  fontWeight: normal
dataSource:
  type: PAGE
  value: ""
  dateField: {}
fillTheScreen: true
enableMainContainerShadow: false
cellStyle:
  minWidth: 33px
  minHeight: 33px
cellStyleRules: []
```

---

## License

Vault content (notes, templates, and CSS snippets) is licensed under the [MIT License](LICENSE).

Bundled community plugins, the `Things` theme, and the images in `Pictures/` are third-party work under their own licenses. 
See [NOTICE](NOTICE) for attribution.