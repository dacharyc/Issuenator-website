---
title: "Getting Started"
weight: 10
description: "Install Issuenator and start tracking issues"
date: 2026-01-01
---

## Installation

Download Issuenator from the [Mac App Store](#).

## Requirements

- macOS 14.0 (Sonoma) or later
- A GitHub account
- A GitHub personal access token

## Setting Up Your API Key

Issuenator uses the GitHub GraphQL API to fetch issues from your repositories. You'll need to create a personal access token:

### Creating a Fine-Grained Token (Recommended)

1. Go to [GitHub Settings > Developer settings > Personal access tokens > Fine-grained tokens](https://github.com/settings/tokens?type=beta)
2. Click "Generate new token"
3. Give it a descriptive name like "Issuenator"
4. Set an expiration (or no expiration)
5. Under "Repository access", choose which repos to grant access
6. Under "Permissions", enable:
   - **Issues**: Read-only
   - **Metadata**: Read-only
   - **Pull requests**: Read-only (for linked PR information)
7. Click "Generate token" and copy it

### Creating a Classic Token

1. Go to [GitHub Settings > Developer settings > Personal access tokens > Tokens (classic)](https://github.com/settings/tokens)
2. Click "Generate new token (classic)"
3. Give it a descriptive name
4. Select scopes:
   - `repo` (for private repositories)
   - `public_repo` (for public repositories only)
5. Click "Generate token" and copy it

### Adding the Token to Issuenator

1. Open Issuenator
2. You'll be prompted to enter your API key on first launch
3. Paste your token and click Save
4. The token is stored securely in your macOS Keychain

## Adding Repositories

Once your API key is configured:

1. Click the **+** button or use **Cmd+Ctrl+A**
2. Enter the repository in `owner/repo` format (e.g., `apple/swift`)
3. Click Add

Issuenator will fetch all open issues from the repository. Depending on the repository size, this may take a moment.

## Next Steps

- Learn about the different [Dashboards](../dashboards/) and how to use them
- Set up [Filters & Tags](../filters-tags/) to organize issues automatically
- Customize [Settings](../settings/) to match your workflow
