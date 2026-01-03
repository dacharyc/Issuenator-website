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
4. Set an expiration
5. Under "Repository access", choose which repos to grant access
6. Under "Permissions > Repository permissions", enable:
   - **Issues**: Read-only
   - **Metadata**: Read-only
   - **Pull requests**: Read-only (for linked PR information)
7. Under "Permissions > Account permissions", enable:
   - **Profile**: Read and write (for your username and avatar). We only need read permission, but GitHub doesn't expose read-only for Profile.
8. Click "Generate token" and copy it

### Creating a Classic Token

1. Go to [GitHub Settings > Developer settings > Personal access tokens > Tokens (classic)](https://github.com/settings/tokens)
2. Click "Generate new token (classic)"
3. Give it a descriptive name
4. Set an expiration
5. Select scopes:
   - `repo`
   - `user`
6. Click "Generate token" and copy it

### Adding the Token to Issuenator

1. Open Issuenator
2. You'll be prompted to enter your API key on first launch
3. Paste your token and click Save
4. The token is stored securely in your macOS Keychain

## Adding Your First Repository

Once your API key is configured:

1. Enter the full GitHub URL (e.g., `https://github.com/apple/swift`)
2. Choose a color for the repository label
3. Optionally customize fetch frequency and archive settings
4. Click **Add Repository**

Issuenator will fetch all open issues from the repository. Depending on the repository size, this may take a moment.

## Adding More Repositories

After initial setup, use **Cmd+Ctrl+A** or **Repositories → Add Repository** to add more repos.

### Add One at a Time

1. On the **Add One** tab, enter the full GitHub URL (e.g., `https://github.com/apple/swift`)
2. Optionally set a custom display name
3. Choose a color for the repository
4. Click **Add Repository**

### Add Multiple Repositories

Need to add several repos at once? Use bulk import:

1. Select the **Add Many** tab
2. Enter full repository URLs, one per line:
   ```
   https://github.com/apple/swift
   https://github.com/facebook/react
   https://github.com/microsoft/vscode
   ```
3. Click **Add Repositories**

Colors are automatically assigned to each repository. Issuenator will validate each URL and fetch all open issues.

## Next Steps

- Learn about the different [Dashboards](../dashboards/) and how to use them
- Set up [Filters & Tags](../filters-tags/) to organize issues automatically
- Customize [Settings](../settings/) to match your workflow
