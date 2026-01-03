---
title: "Features"
description: "Everything Issuenator does to help you manage GitHub Issues"
date: 2026-01-01
---

## A Dedicated Issue Tracker for Maintainers

Issuenator is built specifically for open source maintainers who need to track issues across multiple repositories without drowning in GitHub notifications.

### Smart Dashboards

Issuenator organizes your issues into purpose-built dashboards:

- **Inbox** - New issues on your repos plus issues with updates that need triage
- **Watching** - Issues you've explicitly chosen to keep an eye on
- **My Issues** - Issues you authored, automatically tracked
- **Assigned** - Issues assigned to you (hidden when empty)
- **Inactive** - Open issues with no activity for a configurable number of days
- **Ignored** - Issues you've dismissed from your attention
- **Tagged** - Cross-repository view filtered by your custom tags
- **Archived** - Closed issues kept for reference
- **Per-Repository** - Filter any dashboard to a single repo, or view a dedicated repo-specific dashboard

### Visual Scanning

Designed for quick triage, not endless reading:

- Repository color bars for instant recognition
- Bold comment counts when there are new comments
- Background color shifts for issues with updates
- "New" badges on freshly created issues
- GitHub label colors preserved
- Author avatars and assignee display

### Issue Details

When you need to dive deeper:

- Full issue metadata (author, assignees, labels, milestone, reactions)
- Linked Pull Requests with their current state
- Markdown-rendered description
- Complete comment thread with reactions
- Collapsible already-viewed comments
- Quick actions: Watch, Ignore, Flag, Tag

### Private Tags

Organize issues your way without touching GitHub:

- Create custom tags with 8 color options
- Apply tags manually or automatically via filters
- Tags stay completely local - never synced to GitHub
- View all tagged issues across repos in one place
- Visually distinct from GitHub labels

**Use Cases**
- Tag issues from specific authors as VIP
- Privately tag "Won't Do" where you can't publicly say that for Reasons
- Tag issues related to specific features to get a view of how features impact work across repositories

### Automatic Filters

Set up rules to categorize incoming issues:

- Filter by author, title, body text, repository, or labels
- Actions: Ignore, Watch, Apply tag, Flag as important
- Combine multiple conditions with Any/All/None logic
- Rules apply automatically when issues are fetched

### Bulk Operations

When you need to process many issues at once, bulk operations mode lets you work efficiently.

**How It Works**
- Press Cmd+B to enter bulk operations mode
- Click issues to select them (selection count displays in the toolbar)
- Choose an action: Tag, Archive, Watch, Ignore, or Flag
- All selected issues are updated at once

**Use Cases**
- Tag all issues related to a release
- Archive a batch of resolved issues
- Ignore a flood of bot-generated issues
- Watch all issues from a new contributor

Bulk operations respect dashboard context. You'll only see actions that make sense for the current view.

### Smart Lifecycle Management

Issues move through your dashboards intelligently:

- Configurable inactive threshold (issues with no activity)
- Relationship-based archive timing (different rules for each dashboard)
- Auto-reactivation when inactive issues get new activity
- @mentions automatically un-ignore ignored issues

### Background Sync

Stay up to date without manual refreshing:

- Automatic fetching at configurable intervals
- Per-repository frequency overrides
- Manual fetch available anytime
- Efficient incremental updates via GitHub GraphQL API

### Per-Repository Settings

Customize behavior for each repo:

- Custom display names and colors
- Override archive and inactive thresholds
- Adjust fetch frequency
- Configure label display priority

### Native macOS Experience

Issuenator is built specifically for Mac using Apple's SwiftUI framework, not a web app wrapped in Electron.

**What This Means for You**
- Fast, responsive interface that feels like a native Mac app
- Respects your system preferences (light mode, dark mode, accent colors)
- Full VoiceOver and accessibility support
- Efficient memory and battery usage
- Works offline with locally stored data

### No Subscription, No Account

Unlike many developer tools, Issuenator is a one-time purchase with no recurring fees. You don't need to create an Issuenator account. Just add your GitHub token and start organizing.

- Buy once, own forever
- No account registration required
- No usage limits or feature tiers
- All your data stays on your Mac
