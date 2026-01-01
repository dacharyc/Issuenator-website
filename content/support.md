---
title: "Support"
description: "Get help with Issuenator"
date: 2026-01-01
---

## Get Help

Having trouble with Issuenator? Here's how to get support.

### GitHub Issues

The best way to report bugs or request features is through GitHub Issues:

- [Report a Bug](https://github.com/dacharyc/Issuenator/issues/new?template=bug_report.md)
- [Request a Feature](https://github.com/dacharyc/Issuenator/issues/new?template=feature_request.md)

### Common Questions

**How do I get a GitHub API token?**

Issuenator requires a GitHub personal access token to fetch your issues. You can create one at [github.com/settings/tokens](https://github.com/settings/tokens). See the [API Key documentation](/docs/api-key/) for required permissions.

**Why don't I see issues from a private repository?**

Make sure your GitHub token has access to the repository. For fine-grained tokens, you need to explicitly grant access to each private repository.

**How often does Issuenator fetch new issues?**

By default, Issuenator fetches issues every 15 minutes. You can adjust this in Settings, either globally or per-repository.

**Where is my data stored?**

All data is stored locally on your Mac using SwiftData. Your GitHub token is stored securely in the macOS Keychain. Nothing is sent to any server other than GitHub's API.

### Contact

For other inquiries, you can reach the developer:

- Mastodon: [@dacharyc](https://hachyderm.io/@dacharyc)
- Website: [dacharycarey.com](https://dacharycarey.com)
