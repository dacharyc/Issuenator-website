---
title: "API Key Setup"
weight: 50
description: "GitHub token requirements and configuration"
date: 2026-01-01
---

Issuenator requires a GitHub personal access token to fetch issues from your repositories.

## Token Types

GitHub offers two types of personal access tokens:

### Fine-Grained Tokens (Recommended)

Fine-grained tokens offer more precise control over permissions and repository access.

**Required Permissions:**

| Permission | Access Level | Purpose |
|------------|--------------|---------|
| Issues | Read-only | Fetch issue data |
| Metadata | Read-only | Repository information |
| Pull requests | Read-only | Linked PR information |

**Repository Access:**

Choose between:
- **All repositories** - Token works with any repo you have access to
- **Selected repositories** - Explicitly choose which repos the token can access

### Classic Tokens

Classic tokens use broader OAuth scopes.

**Required Scopes:**

| Scope | Purpose |
|-------|---------|
| `repo` | Full access (required for private repos) |
| `public_repo` | Public repos only (if you only track public repos) |

## Creating Your Token

### Fine-Grained Token

1. Go to [GitHub Settings > Developer settings > Fine-grained tokens](https://github.com/settings/tokens?type=beta)
2. Click **Generate new token**
3. Set a name: "Issuenator"
4. Set expiration (recommended: 90 days or custom)
5. Choose repository access
6. Set permissions (Issues, Metadata, Pull requests: Read-only)
7. Click **Generate token**
8. **Copy the token immediately** - you won't see it again

### Classic Token

1. Go to [GitHub Settings > Developer settings > Tokens (classic)](https://github.com/settings/tokens)
2. Click **Generate new token (classic)**
3. Set a name: "Issuenator"
4. Set expiration
5. Check `repo` (or `public_repo` for public repos only)
6. Click **Generate token**
7. **Copy the token immediately**

## Token Storage

Your token is stored securely in the macOS Keychain:

- Encrypted at rest
- Protected by your macOS login
- Accessible only to Issuenator
- Never sent anywhere except GitHub's API

## Token Expiration

If you set an expiration date:

- Issuenator shows the expiration date in Settings
- Create a new token before expiration
- Update the token in Settings > API Key

## Troubleshooting

### "Bad credentials" Error

- Token may have expired
- Token may have been revoked
- Check [GitHub token settings](https://github.com/settings/tokens) for status

### Missing Private Repositories

- Fine-grained tokens: Add the repository to "Selected repositories"
- Classic tokens: Ensure `repo` scope is enabled (not just `public_repo`)

### SAML SSO Organizations

If your organization uses SAML SSO:

1. Create the token normally
2. Go to [GitHub token settings](https://github.com/settings/tokens)
3. Click **Configure SSO** next to your token
4. Authorize for each organization that requires it
