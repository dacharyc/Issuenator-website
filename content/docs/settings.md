---
title: "Settings"
weight: 40
description: "Configure Issuenator to match your workflow"
date: 2026-01-01
---

Access Settings via **Cmd+,** or from the application menu.

## Global Settings

### Default Dashboard

Choose which dashboard opens when you launch Issuenator.

### Inactive Threshold

Number of days without activity before an issue moves to the Inactive dashboard. Issues automatically return when they receive new activity.

**Default:** 14 days

### Archive Timing

How long after an issue closes before it moves to Archived. Different dashboards have different default behaviors:

| Dashboard | Default Behavior |
|-----------|-----------------|
| My Issues | Archive only on acknowledgment |
| Watching | Configurable delay |
| Assigned | Configurable delay |
| Inbox | Configurable delay after closure |
| Ignored | Immediately on closure |

### Fetch Frequency

How often Issuenator automatically fetches new issues from GitHub.

**Options:** 15 minutes, 1 hour, 4 hours, Daily, Manual only

### Display Options

- Show/hide specific dashboards in the sidebar
- Configure issue card information density
- Label display preferences

## Per-Repository Settings

Override global settings for individual repositories:

### Custom Name & Color

Give repositories display names and colors for visual recognition in the issue list.

### Archive Override

Set a custom archive delay for this repository's issues.

### Inactive Override

Set a custom inactive threshold for this repository.

### Fetch Frequency Override

Fetch this repository more or less frequently than the global default.

## API Key Management

### Viewing Token Status

See when your token expires (if expiration was set).

### Updating Your Token

1. Go to Settings > API Key
2. Enter your new token
3. Click Save

The new token is validated before saving. Your old token is replaced in Keychain.

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| Cmd+, | Open Settings |
| Cmd+K | Manage API Key |
| Cmd+Ctrl+A | Add Repository |
| Cmd+Ctrl+M | Manage Repositories |
| Cmd+Ctrl+W | Watch an Issue by URL |
| Cmd+Ctrl+T | Manage Tags |
| Cmd+Ctrl+G | Apply Tag to Issue |
| Ctrl+F | Create Filter |
| Ctrl+M | Manage Filters |
