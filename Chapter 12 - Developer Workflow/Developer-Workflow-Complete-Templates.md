# Developer Workflow - Complete Templates

Copy-paste ready templates for the Developer Workflow. All fields are blank - fill them in with your own content.

---

## Table of Contents

1. [Technical Decision Record (TDR)](#technical-decision-record-tdr)
2. [Code Snippet](#code-snippet)
3. [Architecture Documentation](#architecture-documentation)
4. [Troubleshooting Log](#troubleshooting-log)
5. [TIL (Today I Learned)](#til-today-i-learned)
6. [API Endpoint Documentation](#api-endpoint-documentation)
7. [Daily Developer Log](#daily-developer-log)
8. [Git Commit Message Template](#git-commit-message-template)

---

## Technical Decision Record (TDR)

```markdown
---
type: decision
project:
date:
status:
tags:
---

# TDR-### : [Decision Title]

## Status

## Context

## Decision

## Alternatives Considered

### Alternative 1
**Pros:**
**Cons:**

### Alternative 2
**Pros:**
**Cons:**

## Rationale

## Consequences

**Positive:**

**Negative:**

## Implementation Notes

## Related Decisions

## References

---
**Author:**
**Reviewers:**
**Discussion:**
```

---

## Code Snippet

```markdown
---
type: snippet
language:
category:
tags:
---

# Snippet - [Problem Description]

## Problem

## Solution

## Code

## Explanation

## When to Use

## When NOT to Use

## Performance Notes

## Related

---
**Created:**
**Last Used:**
```

---

## Architecture Documentation

```markdown
---
type: architecture
project:
updated:
---

# [Project] - System Architecture

## Overview

## Components

### Frontend

### Backend Services

### Infrastructure

## Data Flow

## Design Decisions

## Deployment

## Security

## Monitoring & Alerts

## Future Improvements

---
**Related:**
```

---

## Troubleshooting Log

```markdown
---
type: troubleshooting
project:
date:
severity:
resolved:
---

# Issue - [Problem Description]

## Symptoms

## Investigation

### Step 1:

### Step 2:

## Root Cause

## Solution

### Immediate:

### Short-term:

### Long-term:

## Results

## Prevention

## Related

---
**Time to Resolve:**
**Impact:**
**Postmortem:**
```

---

## TIL (Today I Learned)

```markdown
---
type: til
topic:
date:
tags:
---

# TIL - [What You Learned]

## What I Learned

## Code Example

## Key Points

## When to Use

## When NOT to Use

## Performance Impact

## Related Concepts

---
**Source:**
```

---

## API Endpoint Documentation

```markdown
---
type: api-reference
project:
service:
updated:
---

# API - [Endpoint Name]

## Endpoint

## Description

## Authentication

## Parameters

### Path Parameters

### Query Parameters

## Request Example

## Response Example

### Success

### Error

## Error Codes

## Rate Limiting

## Notes

## Implementation

## Tests

---
**Related:**
```

---

## Daily Developer Log

```markdown
# Dev Log - [Date]

## Project:

### Goals Today
- [ ]

### Accomplished
- ✅

### Blockers

### Decisions Made

### Learned Today

### Tomorrow
- [ ]

### Notes

---
**Time Logged:**
**Meetings:**
**Focus Time:**
```

---

## Git Commit Message Template

```markdown
# Git Commit Message Template

## Format
```
<type>(<scope>): <subject>

<body>

<footer>
```

## Types
- **feat:** New feature
- **fix:** Bug fix
- **docs:** Documentation only
- **style:** Formatting, no code change
- **refactor:** Code restructuring, no behavior change
- **perf:** Performance improvement
- **test:** Adding/updating tests
- **chore:** Build process, dependencies, etc.

## Example
```
fix(auth): resolve JWT expiration edge case

Users with tokens issued exactly at midnight experienced
premature expiration due to timezone handling bug.

Changed expiration calculation to use UTC consistently
and added 5-second grace period.

Fixes #142
```
```

---

## Snippet Index Template

```markdown
# Snippet Index

## By Language

### Python

### JavaScript

### Shell

## By Category

### Performance Optimization

### Error Handling

### Data Processing
```

---

**That's it!** Copy any template, fill in your details, and start documenting.
