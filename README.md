# PM DocStudio

> A fully offline, zero-dependency, single-file HTML workspace for Product Managers to write, preview, and export professional PM documents directly in your browser.

![Type](https://img.shields.io/badge/type-Single%20HTML%20File-1e7a5a?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)
![Dependencies](https://img.shields.io/badge/dependencies-none-brightgreen?style=flat-square)
![Works Offline](https://img.shields.io/badge/works-offline-orange?style=flat-square)

---

## Table of Contents

- [What's Inside](#-whats-inside)
- [How to Use](#-how-to-use)
- [Export Options](#-export-options)
- [JSON Export & Schema](#-json-export--schema)
- [File Structure](#-file-structure)
- [Roadmap](#️-roadmap)
- [Contributing](#-contributing)

---

## What's Inside

Six complete PM document types, each with structured form fields, a live preview panel, PM coaching tips, and context-specific export options.

| # | Document | What it's for |
|---|---|---|
| 📝 | **User Story** | As a / I want / So that rows, acceptance criteria, dependencies |
| 📋 | **PRD** | Problem, goals, metrics, requirements, risks, timeline |
| 🗺️ | **Roadmap** | Vision, Q1–Q4 themes, OKRs, dependencies |
| ⚡ | **Sprint Plan** | Sprint goal, backlog table, capacity, blockers |
| 💡 | **Opportunity Brief** | Problem, opportunity, solution space, why now/why us |
| 📊 | **Gantt Chart** | Week-by-week timeline, owners, status, progress bars |

---

##  How to Use

### Step 1 — Open the app
Download `pm-doc-studio.html` and open it in any modern browser (Chrome, Firefox, Edge, Safari). No installation needed.

```bash
open pm-doc-studio.html          # macOS
start pm-doc-studio.html         # Windows
xdg-open pm-doc-studio.html      # Linux
```

### Step 2 — Pick your document type
Use the **top navigation tabs** or the **left sidebar** to switch between document types. Each switch gives you a fresh structured form, a contextual PM tip, and a completion progress bar.

### Step 3 — Fill in the form
Every document is divided into collapsible sections marked `Required` or `Optional`. The **Live Preview** panel on the right updates in real time as you type.

**Gantt Chart** expands to full width with an inline task editor:
- Add task name, owner, start week, duration, status, and % done
- Click the colored dot to cycle through 8 task colors
- Set "Today = Week N" to show a red today marker
- Choose timeline from 4–24 weeks

### Step 4 — Export your document
Click **Export Document** in the bottom-right panel. Each document type shows only formats that make sense for it:

- **⬇ Download** — saves a file to your computer (PDF, Word, CSV, JSON, PowerPoint)
- **📋 Copy + Open** — copies your content to clipboard, then opens the tool in a new tab
- **↗ Open** — opens the destination tool directly

---

## Export Options

### User Story
| Format | Action | Best for |
|---|---|---|
| PDF | ⬇ Download | Confluence, email, stakeholder review |
| Word (.docx) | ⬇ Download | Microsoft Word, Google Docs, LibreOffice |
| **JSON** | ⬇ Download | Import into Jira, Linear, Asana via API |
| Jira | ↗ Open | Create Jira issue |
| Linear | 📋 Copy + Open | Paste into Linear issue |
| Asana | ↗ Open | Create Asana task |
| Google Docs | 📋 Copy + Open | Open new doc and paste |

### PRD
| Format | Action | Best for |
|---|---|---|
| PDF | ⬇ Download | Formal stakeholder distribution |
| Word (.docx) | ⬇ Download | Editable in Word / Google Docs |
| **JSON** | ⬇ Download | Import to Notion, Confluence via API |
| Notion | 📋 Copy + Open | Paste into Notion page |
| Confluence | ↗ Open | Create Confluence page |
| Google Docs | 📋 Copy + Open | Open new doc and paste |
| Google Slides | 📋 Copy + Open | Present your PRD |

### Roadmap
| Format | Action | Best for |
|---|---|---|
| PDF | ⬇ Download | Stakeholder distribution |
| PowerPoint | ⬇ Download | HTML slide deck (open in browser → print as PDF) |
| **JSON** | ⬇ Download | Import to Productboard, Miro via API |
| FigJam | ↗ Open | Visual roadmap board |
| Miro | ↗ Open | Collaborative roadmap board |
| Productboard | ↗ Open | Import initiatives |
| Google Slides | 📋 Copy + Open | Present the roadmap |

### Sprint Plan
| Format | Action | Best for |
|---|---|---|
| PDF | ⬇ Download | Printable plan for standups |
| Excel / CSV | ⬇ Download | Google Sheets or Excel task table |
| **JSON** | ⬇ Download | Bulk import to Jira / Azure DevOps |
| Jira Board | ↗ Open | Set up sprint in Jira |
| Azure DevOps | ↗ Open | Import to ADO sprint board |
| Google Sheets | 📋 Copy + Open | Open task list in Sheets |
| Notion | 📋 Copy + Open | Paste into Notion sprint board |

### Opportunity Brief
| Format | Action | Best for |
|---|---|---|
| PDF | ⬇ Download | Share with stakeholders |
| Word (.docx) | ⬇ Download | Editable document |
| **JSON** | ⬇ Download | Structured data for Notion / Slite APIs |
| Notion | 📋 Copy + Open | Paste into Notion |
| Slite | ↗ Open | Create note in Slite |
| Google Docs | 📋 Copy + Open | Open new doc and paste |
| Loom | ↗ Open | Record a video walkthrough |

### Gantt Chart
| Format | Action | Best for |
|---|---|---|
| PDF | ⬇ Download | Print-ready Gantt for reviews |
| Excel / CSV | ⬇ Download | Task data in Google Sheets / Excel |
| **JSON** | ⬇ Download | Import to GanttPRO, timeline tools |
| GanttPRO | ↗ Open | Import structured task data |
| Timeline View | 📋 Copy + Open | Google Sheets timeline |
| Google Sheets | 📋 Copy + Open | Open task data in Sheets |
| Notion | 📋 Copy + Open | Paste timeline into Notion |

---

## JSON Export & Schema

Every document exports a **structured, versioned JSON file** with two layers:

1. **Native schema** — all fields exactly as filled in the form
2. **Tool-compatible block** — pre-shaped for direct import into a specific tool

### Schema reference

| Document | Schema ID | Tool-compatible field |
|---|---|---|
| User Story | `pm-docstudio/user-story@1.0` | `jiraCompatible` |
| PRD | `pm-docstudio/prd@1.0` | `notionCompatible` |
| Roadmap | `pm-docstudio/roadmap@1.0` | `productboardCompatible` |
| Sprint Plan | `pm-docstudio/sprint-plan@1.0` | `jiraCompatible` |
| Opportunity Brief | `pm-docstudio/opportunity-brief@1.0` | `notionCompatible` |
| Gantt Chart | `pm-docstudio/gantt@1.0` | `ganttProCompatible` |

### Example — User Story JSON

```json
{
  "schema": "pm-docstudio/user-story@1.0",
  "exportedAt": "2025-02-15T10:30:00.000Z",
  "metadata": {
    "title": "Checkout Guest Mode",
    "author": "Rahul Sharma",
    "epic": "Checkout Redesign",
    "sprint": "Sprint 14",
    "priority": "P1",
    "storyPoints": 5
  },
  "stories": [
    {
      "id": "US-1",
      "asA": "first-time buyer",
      "iWant": "checkout without creating an account",
      "soThat": "I can complete my purchase faster"
    }
  ],
  "acceptanceCriteria": [
    {
      "id": "AC-1",
      "criterion": "Given I am on the checkout page, when I select Guest Checkout, then I can complete payment without signing up"
    }
  ],
  "jiraCompatible": {
    "issueType": "Story",
    "summary": "Checkout Guest Mode",
    "labels": ["pm-docstudio"],
    "priority": "P1",
    "description": "*As a* first-time buyer, *I want to* checkout without creating an account...",
    "acceptanceCriteria": "Given I am on the checkout page..."
  }
}
```

### Example — Sprint Plan JSON (Jira bulk import)

```json
{
  "schema": "pm-docstudio/sprint-plan@1.0",
  "jiraCompatible": {
    "sprintName": "Sprint 14",
    "sprintGoal": "Enable guest checkout without drop-off",
    "issues": [
      {
        "issueType": "Task",
        "summary": "Build guest checkout flow",
        "assignee": "Dev Team",
        "storyPoints": 8,
        "status": "To Do"
      }
    ]
  }
}
```

### How to use JSON with tools

| Tool | How to use the JSON |
|---|---|
| **Jira** | Use Jira REST API `POST /rest/api/3/issue` with the `jiraCompatible` block |
| **Notion** | Use Notion API `POST /v1/pages` with the `notionCompatible` block as page properties |
| **Productboard** | Use `productboardCompatible.initiatives` array with the Productboard API |
| **GanttPRO** | Use `ganttProCompatible.tasks` with GanttPRO's import feature |
| **Any tool** | The native schema gives you clean, structured data you can map to any API |

---

## 📁 File Structure

```
pm-docstudio/
├── pm-doc-studio.html   ← Entire app (HTML + CSS + JS, single file ~2700 lines)
└── README.md            ← This file
```

No `package.json`. No `node_modules`. No build step. One file.

---

## Roadmap

- [ ] Local storage — save drafts between sessions
- [ ] Import JSON — load a previously exported doc back into the editor
- [ ] Dark mode toggle
- [ ] Share via URL (content encoded in URL hash)
- [ ] Jira / Linear direct API integration
- [ ] Multi-story sprint linking
- [ ] Custom template builder

---


### Adding a new document type

```javascript
// 1. Add to EXPORT_CONFIG
'my-doc': {
  label: 'My Doc',
  downloads: [
    { id:'pdf',  icon:'🖨', bg:'#fceef1', name:'PDF',  desc:'...', badge:'download' },
    { id:'json', icon:'{}', bg:'#f0fdf4', name:'JSON', desc:'...', badge:'download' },
  ],
  tools: [ ... ]
}

// 2. Add renderMyDoc() template function
// 3. Add JSON schema branch inside exportJSON()
// 4. Register in the templates map inside switchDoc()
// 5. Add nav tab and sidebar item in HTML
```

---

## License

MIT — free to use, modify, and distribute. Attribution appreciated but not required.

---

> Built for PMs who want to write better documents faster without fighting templates in Notion or Confluence.

## Live Demo


## Built By

**Anshuman Jaiswal**  
Associate Product Manager  
Building thinking systems in public.

---

## If This Helps You

- ⭐ Star the repo  
- Share with someone who is preparing for PM interviews or started as a Junior PM 
- Improve it and raise a PR  

Let’s raise the bar for Product thinking.
