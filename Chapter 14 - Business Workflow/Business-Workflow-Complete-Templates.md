# Business/Productivity Workflow - Complete Templates

Copy-paste ready templates for the Business/Productivity Workflow. All fields are blank - fill them in with your own content.

---

## Table of Contents

1. [Daily Note](#daily-note)
2. [Meeting Note](#meeting-note)
3. [Person Note (CRM)](#person-note-crm)
4. [Project Dashboard](#project-dashboard)
5. [Annual Goals](#annual-goals)
6. [Monthly Goal Review](#monthly-goal-review)
7. [Decision Record](#decision-record)
8. [Weekly Review](#weekly-review)
9. [Master Dashboard](#master-dashboard)

---

## Daily Note

```markdown
---
date:
day:
tags: daily
---

# [Date] - [Day]

## Top 3 Priorities
1.
2.
3.

## Schedule

## Tasks

### Must Do Today

### Should Do (if time)

### Waiting On

## Meetings

## Notes

## Ideas

## Decisions Made

## Tomorrow's Setup

---
**Energy Level:**
**Mood:**
**Wins:**
```

---

## Meeting Note

```markdown
---
type: meeting
date:
attendees:
project:
tags: meeting
---

# Meeting - [Title]

**Date:**
**Location:**
**Type:**

## Attendees

## Agenda

## Discussion

## Action Items

## Decisions Made

## Next Meeting

---
**Related:**
```

---

## Person Note (CRM)

```markdown
---
type: person
category:
company:
tags:
---

# [Name]

## Basic Info

## Context

## Current Projects

## Interaction Log

### [Date] - [Interaction Type]

## Notes & Preferences

## Follow-Up Items

## Related

---
**Last Contact:**
**Next Follow-Up:**
**Relationship Status:**
```

---

## Project Dashboard

```markdown
---
type: project
status:
priority:
start:
deadline:
owner:
budget:
---

# Project - [Name]

## Overview

## Status

## Key Metrics

## Milestones

## Team

## Weekly Status

### This Week

**Accomplished:**

**Blocked:**

**Next Week:**

## Budget Breakdown

## Risks & Issues

### High Priority

### Medium Priority

### Low Priority

## Decisions Log

## Key Documents

## Stakeholder Updates

---
**Last Updated:**
**Next Review:**
```

---

## Annual Goals

```markdown
---
type: goals
year:
tags: goals, okr
---

# [Year] Annual Goals

## Theme:

## Professional Goals

### Goal 1:
**Target:**

**Key Results:**

**Progress:**

**Strategies:**

### Goal 2:

## Personal Goals

### Goal 1:

## Quarterly Review Schedule

## Monthly Check-Ins

---
**Created:**
**Last Reviewed:**
**Next Review:**
```

---

## Monthly Goal Review

```markdown
---
type: goal-review
period:
tags: goals, review
---

# [Month Year] - Monthly Goal Review

## Professional Progress

### [Goal Category]
**Target:**
**Actual:**

**Analysis:**

### Projects

### Wins

### Challenges

## Personal Progress

### [Goal Category]

**Action:**

### Learning

## Key Learnings This Month

## [Next Month] Focus

### Top 3 Priorities

### Habits to Improve

---
**Overall Assessment:**
**Related:**
```

---

## Decision Record

```markdown
---
type: decision
date:
category:
impact:
---

# Decision - [Title]

## Context

## Decision

## Rationale

### Why [Chosen Option]?

### Why Not [Alternative]?

## Alternatives Considered

### Alternative 1

### Alternative 2

## Consequences

**Positive:**

**Negative:**

## Success Metrics

## Timeline

---
**Decision Made By:**
**Consulted:**
**Related:**
```

---

## Weekly Review

```markdown
---
type: weekly-review
week:
tags: review
---

# Weekly Review - Week [Number] ([Date Range])

## This Week's Daily Notes

## Completed Tasks This Week
```dataview
TASK
FROM "Daily"
WHERE completed
WHERE file.cday >= date([start]) AND file.cday <= date([end])
```

## Projects Progress

### Active Projects

### Completed This Week

## Wins

## Challenges

## Key Learnings

## Next Week's Focus

### Top 3 Priorities

### Habits to Maintain

### Meetings Scheduled

## Admin Tasks

## Ideas Captured This Week

---
**Energy Level (Week Avg):**
**Mood:**
**Overall:**
**Related:**
```

---

## Master Dashboard

```markdown
# Master Dashboard

## Quick Links

## Active Projects
```dataview
TABLE status, deadline, priority
FROM "Projects/Active"
WHERE type = "project"
SORT deadline ASC
```

## This Week's Priorities

## Upcoming Deadlines (Next 14 Days)
```dataview
TABLE deadline, status
FROM "Projects"
WHERE deadline <= date(today) + dur(14 days) AND status != "complete"
SORT deadline ASC
```

## People to Follow Up With
```dataview
TABLE last-contact, next-follow-up
FROM "People"
WHERE next-follow-up <= date(today) + dur(7 days)
SORT next-follow-up ASC
```

## Recent Decisions
```dataview
LIST
FROM "Decisions"
SORT date DESC
LIMIT 5
```

## This Month's Goals Progress

## Quick Capture

---
**Last Updated:**
```

---

**That's it!** Copy any template, fill in your details, and start organizing.
