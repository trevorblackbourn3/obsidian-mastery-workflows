# Appendix F: Glossary of PKM Terms

**Definitions of common terms used in Obsidian and Personal Knowledge Management.**

**Alphabetically organized for quick reference.**

---

## A

### Alias

**Definition:** Alternative name for a note that can be used in links.

**Example:** Note titled "Marcus Reid" with alias "Author" can be linked as `[[Author]]` and will point to "Marcus Reid" note.

**How to use:**
```markdown
---
aliases:
  - Alternative Name
  - Another Name
---
```

**Chapter reference:** 2, 6

---

### Archive

**Definition:** Storage location for completed or inactive notes that you want to keep but don't need in active vault.

**Purpose:** Reduces clutter, improves performance, maintains searchable history.

**Best practice:** Archive notes older than 1 year or completed projects.

**Chapter reference:** 20

---

### Atomic Note

**Definition:** A note that contains one idea, concept, or piece of information.

**Philosophy:** Small, focused notes that can be easily linked and reused.

**Opposite:** Long-form notes containing multiple topics.

**Example:** Instead of "Marketing Strategies" (broad), create "Content Marketing via SEO" (atomic).

**Chapter reference:** 2

---

## B

### Backlink

**Definition:** Automatic reference showing which notes link TO the current note.

**Location:** Right sidebar → Backlinks panel

**Example:** If Note A links to Note B, Note B's backlinks panel shows Note A.

**Purpose:** Discover connections, see context, navigate bidirectionally.

**Chapter reference:** 2, 6

---

### Block Reference

**Definition:** Link to specific paragraph or block within a note.

**Syntax:** `[[Note Name#^block-id]]`

**Creating block ID:**
```markdown
This is a paragraph. ^my-block-id
```

**Chapter reference:** 6

---

## C

### Canvas

**Definition:** Infinite whiteboard for visual organization in Obsidian.

**Use case:** Mind mapping, brainstorming, visual project planning.

**File type:** .canvas

**Chapter reference:** 13, 20

---

### Callout

**Definition:** Formatted block for highlighting information (notes, warnings, tips, etc.).

**Syntax:**
```markdown
> [!note]
> This is a callout.
```

**Types:** note, tip, warning, danger, info, success, etc.

**Chapter reference:** Appendix A

---

### Community Plugin

**Definition:** Third-party plugin created by Obsidian community (not official).

**Installation:** Settings → Community Plugins → Browse

**Examples:** Dataview, Templater, Calendar

**Chapter reference:** 7, 8, Appendix C

---

### Core Plugin

**Definition:** Official plugin included with Obsidian (developed by Obsidian team).

**Examples:** Daily Notes, Templates, Graph View, Backlinks

**Activation:** Settings → Core Plugins → Toggle on/off

**Chapter reference:** 3, 7

---

## D

### Daily Note

**Definition:** Note created automatically for each day, typically for journaling or task tracking.

**Naming convention:** Usually `YYYY-MM-DD.md`

**Plugin:** Core Daily Notes plugin

**Use case:** Journaling, daily tasks, quick capture

**Chapter reference:** 7, 10, 19

---

### Dashboard

**Definition:** Central hub note showing key information (tasks, projects, goals) in one place.

**Features:** Dynamic queries (Dataview), quick links, status overview

**Purpose:** Single-pane-of-glass view of what matters.

**Chapter reference:** 18

---

### Dataview

**Definition:** Community plugin that queries and displays note data dynamically.

**Language:** Dataview Query Language (DQL) or DataviewJS

**Use case:** Creating lists, tables, and dashboards from note metadata.

**Example:**
```dataview
TABLE status, deadline
FROM "Projects"
WHERE status = "active"
```

**Chapter reference:** 15, 18

---

## E

### Embed

**Definition:** Including content from another note or file directly within current note.

**Syntax:**
- Notes: `![[Note Name]]`
- Images: `![[image.png]]`
- PDFs: `![[document.pdf]]`

**Result:** Content appears inline, not just as link.

**Chapter reference:** 6, Appendix A

---

### Evergreen Note

**Definition:** Note that's continually updated and refined over time (not time-bound).

**Philosophy:** Living documents that grow with your understanding.

**Opposite:** Daily notes (time-stamped, not updated).

**Origin:** Andy Matuschak's note-taking methodology.

**Chapter reference:** 2

---

## F

### Folder Note

**Definition:** Note with same name as folder, serving as index or overview for that folder.

**Example:**
```
Projects/
├── Projects.md  ← Folder note
├── Project Alpha.md
└── Project Beta.md
```

**Purpose:** Overview of folder contents.

**Chapter reference:** 4

---

### Frontmatter

**Definition:** YAML metadata block at top of note containing properties.

**Syntax:**
```markdown
---
property: value
tags: [tag1, tag2]
date: 2025-10-03
---
```

**Purpose:** Structured data for queries, organization, metadata.

**Chapter reference:** 5, 15, Appendix A

---

## G

### Graph View

**Definition:** Visual representation of notes and their connections.

**Types:**
- Global graph (entire vault)
- Local graph (current note + connections)

**Use case:** Visualizing knowledge structure, finding connection patterns.

**Chapter reference:** 2, 20

---

## H

### Hotkey

**Definition:** Keyboard shortcut assigned to command.

**Configuration:** Settings → Hotkeys

**Examples:**
- `Ctrl/Cmd + N` → New note
- `Ctrl/Cmd + O` → Quick Switcher

**Chapter reference:** Appendix B

---

## I

### Inbox

**Definition:** Temporary location for quick captures, unprocessed ideas, or imported content.

**Workflow:** Capture → Process → File to appropriate location → Empty inbox.

**Best practice:** Review and empty weekly.

**Chapter reference:** 4, 19

---

## L

### Link

**Definition:** Connection between notes.

**Types:**
- **Wikilink:** `[[Note Name]]`
- **Markdown link:** `[Display](Note.md)`
- **External link:** `[Text](https://url.com)`

**Purpose:** Create knowledge network, enable navigation.

**Chapter reference:** 2, 6

---

### Live Preview

**Definition:** Editor mode showing both markdown source and rendered preview simultaneously.

**Toggle:** Settings → Editor → Default editing mode

**Benefit:** See formatting while typing.

**Chapter reference:** 3

---

### Local Graph

**Definition:** Graph view showing only current note and its immediate connections.

**Access:** Right sidebar → More options → Open local graph

**Benefit:** Less overwhelming than global graph for large vaults.

**Chapter reference:** 20

---

## M

### Markdown

**Definition:** Lightweight markup language for formatting text.

**Syntax examples:**
- `**bold**` → **bold**
- `*italic*` → *italic*
- `# Heading` → Heading

**Why Obsidian uses it:** Plain text, future-proof, portable.

**Chapter reference:** 2, 3, Appendix A

---

### Map of Content (MOC)

**Definition:** Hub note linking to related notes on a topic.

**Purpose:** Navigation, overview, structure.

**Example:** "Writing MOC" linking to all writing-related notes.

**Alternative to:** Folders (more flexible).

**Chapter reference:** 2, 4, 6, 20

---

### Metadata

**Definition:** Data about notes (properties, tags, dates, custom fields).

**Storage:** Frontmatter (YAML) or inline properties.

**Purpose:** Queryable information for Dataview, organization.

**Chapter reference:** 5, 15

---

## O

### Orphan

**Definition:** Note with no links to or from other notes.

**Problem:** Disconnected from knowledge network, hard to rediscover.

**Solution:** Link to MOC, related notes, or delete if unnecessary.

**Finding orphans:**
```dataview
FROM ""
WHERE file.inlinks.length = 0 AND file.outlinks.length = 0
```

**Chapter reference:** 6, 19, 20

---

### Outlink

**Definition:** Link from current note TO another note.

**Opposite:** Backlink (link TO current note).

**View:** Right sidebar → Outgoing links

**Chapter reference:** 6

---

## P

### PARA

**Definition:** Organizational method (Projects, Areas, Resources, Archive).

**Created by:** Tiago Forte

**Purpose:** Action-oriented organization system.

**Chapters:** 4

---

### Plugin

**Definition:** Extension adding functionality to Obsidian.

**Types:** Core plugins (official), Community plugins (third-party)

**Management:** Settings → Plugins

**Chapter reference:** 7, 8, Appendix C

---

### PKM

**Definition:** Personal Knowledge Management - system for capturing, organizing, and using information.

**Tools:** Obsidian, Notion, Roam Research, Evernote, etc.

**Philosophy:** Building "second brain" or external knowledge system.

**Chapter reference:** 1, 2, 24

---

### Properties

**Definition:** Structured metadata fields in frontmatter.

**Syntax:**
```markdown
---
author: Jane Doe
date: 2025-10-03
status: draft
---
```

**Use:** Dataview queries, organization, filtering.

**Chapter reference:** 5, 15

---

## Q

### Query

**Definition:** Search or filter for specific notes or data.

**Types:**
- Search (basic keyword search)
- Dataview query (structured data retrieval)

**Example:**
```dataview
TABLE status FROM "Projects" WHERE status = "active"
```

**Chapter reference:** 15

---

### Quick Switcher

**Definition:** Fast note navigation by typing note name.

**Shortcut:** `Ctrl/Cmd + O`

**Feature:** Fuzzy search (partial matches work).

**Chapter reference:** 3, Appendix B

---

## R

### Reading View

**Definition:** View mode showing only rendered markdown (no source).

**Toggle:** `Ctrl/Cmd + E`

**Use case:** Reading notes without editing.

**Chapter reference:** 3

---

## S

### Second Brain

**Definition:** External system for storing and organizing knowledge (offloading from biological brain).

**Origin:** Book by Tiago Forte

**Tools:** Obsidian, Notion, etc.

**Philosophy:** Capture everything, organize for action, build knowledge over time.

**Chapter reference:** 1, 2

---

### Snippet (CSS)

**Definition:** Custom CSS code for styling Obsidian appearance.

**Location:** `.obsidian/snippets/` folder

**Activation:** Settings → Appearance → CSS Snippets

**Use case:** Customizing theme, layout, colors.

**Chapter reference:** 17

---

### Source Mode

**Definition:** Editor mode showing raw markdown (no rendering).

**Toggle:** Settings → Editor → Default editing mode

**Use case:** Precise editing, avoiding formatting artifacts.

**Chapter reference:** 3

---

### Sync

**Definition:** Synchronizing vault across multiple devices.

**Options:**
- Obsidian Sync (official, paid)
- Third-party (Dropbox, iCloud, Google Drive)
- Git-based (Obsidian Git plugin)

**Chapter reference:** 9, 20, 22

---

## T

### Tag

**Definition:** Label for categorizing notes.

**Syntax:** `#tag` or `#nested/tag`

**Location:** Inline in note or in frontmatter

**Use case:** Grouping related notes, filtering, organization.

**Chapter reference:** 5

---

### Template

**Definition:** Pre-formatted note structure for consistent note creation.

**Plugins:**
- Core Templates plugin (basic)
- Templater plugin (advanced, dynamic)

**Use case:** Daily notes, meeting notes, project templates.

**Chapter reference:** 7, 16, Appendix D

---

### Templater

**Definition:** Advanced templating plugin with dynamic content and scripting.

**Syntax:** `<% ... %>`

**Features:** Date insertion, prompts, calculations, conditional logic.

**Chapter reference:** 16

---

## U

### URI Scheme

**Definition:** URL format for opening Obsidian notes or actions from external apps.

**Syntax:** `obsidian://action?vault=name&file=path`

**Use case:** Linking from task managers, browsers, other apps to Obsidian.

**Examples:**
- `obsidian://open?vault=MyVault&file=Note`
- `obsidian://search?vault=MyVault&query=term`

**Chapter reference:** 22

---

## V

### Vault

**Definition:** Folder containing all your Obsidian notes and configuration.

**Location:** Anywhere on your file system

**Contents:** Markdown files, attachments, `.obsidian/` config folder

**Multiple vaults:** Can have separate vaults for different purposes.

**Chapter reference:** 1, 3

---

## W

### Weekly Review

**Definition:** Regular process (weekly) for maintaining vault health.

**Activities:** Process tasks, link orphans, review projects, clean up.

**Purpose:** Keep system current, prevent degradation.

**Chapter reference:** 19

---

### Wikilink

**Definition:** Obsidian's internal linking syntax using double brackets.

**Syntax:** `[[Note Name]]`

**Benefits:** Simpler than markdown links, auto-complete, creates note if doesn't exist.

**Chapter reference:** 2, 6, Appendix A

---

### Workspace

**Definition:** Saved layout configuration (panes, tabs, sidebars).

**Plugin:** Core Workspaces plugin

**Use case:** Different layouts for different contexts (writing, research, reviewing).

**Chapter reference:** 7

---

## Y

### YAML

**Definition:** Data format used in frontmatter for structured properties.

**Syntax:**
```yaml
key: value
list:
  - item1
  - item2
```

**Chapter reference:** 5, 15, Appendix A

---

## Z

### Zettelkasten

**Definition:** Note-taking method using atomic notes with unique IDs and heavy linking.

**Origin:** Niklas Luhmann (German sociologist)

**Philosophy:** Bottom-up knowledge building through connected atomic notes.

**Implementation in Obsidian:** Atomic notes + wikilinks + tags

**Key principles:**
- One idea per note
- Unique identifiers (or titles)
- Linking between notes
- Emergent structure (not pre-planned)

**Chapter reference:** 2, 6, 11

---

## Acronyms & Abbreviations

**API** - Application Programming Interface (for plugin development)

**CSS** - Cascading Style Sheets (for appearance customization)

**CSV** - Comma-Separated Values (data format)

**DQL** - Dataview Query Language

**GUI** - Graphical User Interface

**HTML** - HyperText Markup Language

**JSON** - JavaScript Object Notation (configuration files)

**KDP** - Kindle Direct Publishing (Amazon)

**MOC** - Map of Content

**PARA** - Projects, Areas, Resources, Archive

**PDF** - Portable Document Format

**PKM** - Personal Knowledge Management

**URI** - Uniform Resource Identifier

**URL** - Uniform Resource Locator

**YAML** - YAML Ain't Markup Language (recursive acronym)

---

## Related Methodologies

### Building a Second Brain (BASB)

**Creator:** Tiago Forte

**Key concepts:** CODE (Capture, Organize, Distill, Express), PARA method

**Focus:** Action-oriented knowledge management

---

### Linking Your Thinking (LYT)

**Creator:** Nick Milo

**Key concepts:** Maps of Content, fluid frameworks, idea emergence

**Focus:** Flexible, adaptive knowledge structures

---

### Getting Things Done (GTD)

**Creator:** David Allen

**Key concepts:** Capture, clarify, organize, reflect, engage

**Focus:** Task and project management

**Integration with Obsidian:** Can use Obsidian for GTD context lists, project plans, reference material

---

### Progressive Summarization

**Creator:** Tiago Forte

**Technique:** Layer 1 (capture), Layer 2 (bold), Layer 3 (highlight), Layer 4 (summary)

**Purpose:** Distill information to essence over time

---

## Common Obsidian Jargon

**"Vaulting"** - Working in Obsidian vault

**"Link thinking"** - Building knowledge through connections (not folders)

**"Evergreening"** - Updating and refining notes over time

**"Gardening"** - Tending to digital garden (maintaining notes)

**"Emergence"** - Structure appearing from use (not pre-planned)

**"Friction"** - Resistance in workflow (good PKM reduces friction)

---

**Bookmark this glossary for quick reference.**

**When you encounter unfamiliar term in Obsidian community, check here first.**

**Understanding terminology accelerates learning and communication.**
