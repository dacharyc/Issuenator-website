---
title: "Filters & Tags"
weight: 30
description: "Organize issues with automatic filters and custom tags"
date: 2026-01-01
---

## Custom Tags

Tags are your personal organization system. Unlike GitHub labels, tags:

- Stay completely local on your Mac
- Never sync to GitHub
- Work across all repositories
- Can be applied manually or automatically

### Creating Tags

1. Open **Tags** from the menu (Cmd+Ctrl+T)
2. Click **New Tag**
3. Enter a name and choose from 8 pastel colors
4. Click Save

### Applying Tags

**Manually:**
- In issue detail view, click the Tag button
- Right-click an issue card and select from your tags

**Automatically:**
- Create an automatic filter with a "Apply tag" action

### Viewing Tagged Issues

The **Tagged** dashboard shows all tagged issues across repositories. Use the filter to view specific tags.

---

## Automatic Filters

Automatic filters categorize incoming issues based on rules you define. When issues are fetched, matching filters apply their actions automatically.

### Creating a Filter

1. Open **Filters** from the menu (Ctrl+F)
2. Click **New Filter**
3. Define your conditions and action
4. Click Save

### Filter Conditions

Build conditions using:

| Field | Description |
|-------|-------------|
| Author | GitHub username of issue creator |
| Title | Issue title text |
| Body | Issue description text |
| Repository | Repository name |
| Label | GitHub label name |

### Operators

| Operator | Description |
|----------|-------------|
| Equals | Exact match |
| Includes | Contains the text |
| Does not equal | Exact non-match |
| Does not include | Does not contain the text |

### Condition Logic

Combine multiple conditions with:

- **Any of** - Matches if any condition is true (OR)
- **All of** - Matches only if all conditions are true (AND)
- **None of** - Matches only if no conditions are true (NOR)

### Filter Actions

When an issue matches a filter:

| Action | Effect |
|--------|--------|
| Ignore | Move to Ignored dashboard |
| Watch | Move to Watching dashboard |
| Apply tag | Add a specific tag |
| Flag important | Mark as important |

### Examples

**Ignore bot-created issues:**
- Condition: Author includes "bot"
- Action: Ignore

**Tag security issues:**
- Condition: Label equals "security"
- Action: Apply tag "Security"

**Watch issues mentioning your project:**
- Condition: Body includes "my-project-name"
- Action: Watch

### Filter Evaluation

- All matching filters apply (they compose, not compete)
- Filters run when issues are fetched
- Existing issues aren't retroactively filtered
