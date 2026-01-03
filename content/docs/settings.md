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

| Option | Description |
|--------|-------------|
| Several times per hour | Most frequent updates |
| **Hourly** (default) | Balanced freshness and API usage |
| Several times per day | Reduced API calls |
| Daily | Minimal API usage |

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

### Navigation

| Shortcut | Action |
|----------|--------|
| Cmd+1 | Go to Inbox |
| Cmd+2 | Go to Watching |
| Cmd+3 | Go to My Issues |
| Cmd+4 | Go to Assigned |
| Cmd+5 | Go to Inactive |
| Cmd+6 | Go to Ignored |
| Cmd+7 | Go to Tagged |
| Cmd+8 | Go to Archived |
| Cmd+F | Focus Search |

### Issues

| Shortcut | Action |
|----------|--------|
| Cmd+B | Toggle Bulk Operations |
| T | Apply Tags to Selected Issue |
| Cmd+Ctrl+W | Watch an Issue by URL |

### Repositories

| Shortcut | Action |
|----------|--------|
| Cmd+Ctrl+A | Add Repository |
| Cmd+Ctrl+M | Manage Repositories |

### Tags

| Shortcut | Action |
|----------|--------|
| Cmd+Ctrl+T | Create Tag |
| Cmd+Ctrl+G | Manage Tags |

### Filters

| Shortcut | Action |
|----------|--------|
| Ctrl+F | Create Filter |
| Ctrl+M | Manage Filters |

### App

| Shortcut | Action |
|----------|--------|
| Cmd+, | Open Settings |
| Cmd+K | Manage API Key |
| Cmd+L | View Logs |
| Cmd+D | View Documentation |

## Activity Logs

Issuenator keeps a log of app activity during each session—useful for troubleshooting or understanding what happened during a fetch.

**Viewing Logs**
- Press Cmd+L or choose Logs → View Logs
- Logs show fetch operations, errors, and app events
- Logs are kept in memory only and cleared when you quit the app
- You can export logs to a file for support requests
