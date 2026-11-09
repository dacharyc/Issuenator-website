---
title: "Agent Server and MCP Access"
weight: 45
description: "Issuenator lets you collaborate with your favorite agents"
date: 2026-11-08
---

Issuenator provides an optional **Agent Server** you can enable to let your favorite agent perform actions in Issuenator through MCP. This setting is disabled by default; when you enable it, Issuenator runs a local server that enables MCP access.

## What your agent can do

The Agent Server is designed to let your agent help you manage issues, including:

- Summarize new activity for you
- Plan work based on tags related to issue priority or other details that only exist locally in Issuenator, not in GitHub
- Triage incoming requests on your behalf by applying tags, proposing filters, and clearing notifications
- Manage the repositories and issues you watch through Issuenator

The agent works through MCP tools that enable it to access things you can also do in the UI, such as:

- List issues, including seeing custom tags you've applied or whether you've seen updates
- Add and remove repositories
- Create filters
- Mark inbox items and updates as viewed
- Create and apply tags
- Archive and delete issues

Everything an agent does gets a UI indicator so you can keep an eye on what agents are doing, and decide whether to accept or revert agent changes. For example:

- Agent-proposed filters get an `Agent` label next to the name in the Manage Filters UI
- Issues where agents have taken some action get a new `Agent Activity` section that summarizes the actions an agent has done
- You can access an Agent Actions UI that aggregates all pending, approved, and reverted actions an agent has taken in the app, so you can bulk accept or revert or see a history of what the agent has done
- Agent activities appear in the app log as a filterable drop-down, and there is a separate agent actions log you can view and export if you need it for compliance activities

### Performing destructive actions

The Agent Server holds destructive actions for your approval.

In the Issuenator UI, you can view pending destructive actions in **Agent Actions** and approve or decline them.

If your agent harness supports it, Issuenator also uses an MCP protocol feature called elicitation to have the harness client ask for human approval when taking destructive actions. This shows up as a dialog in your terminal or GUI asking you to approve or deny the action the agent has proposed.

Most destructive actions can be reverted, but a few of them can't, including:

- Removing a repository from Issuenator; once a repository is removed, all of its watched issues and Issuenator history is also removed
- Ignoring an issue in a repository you're not watching; once you ignore it, it is removed from Issuenator
- Clearing archived issues; once archived issues are deleted, no history is retained in Issuenator

The Agent Server takes extra care around these activities, which is why we request human approval when an agent attempts to perform them. However, this extra approval step is only available in harnesses that support MCP elicitation.

The full list of destructive actions that Issuenator holds pending approval includes:

- Issues
  - Mark viewed
  - Ignore
  - Archive
  - Delete
- Repositories
  - Remove repositories

### Approve or Revert Agent Actions

Issuenator provides several ways to approve or revert agent writes:

#### Issues

In any issue where an agent has taken actions, you'll see an `Agent Activity` section. Use the buttons to Accept or Revert the actions listed there.

#### Filters

In the **Filters** -> **Manage Filters** view, you can see a list of all filters. Any filter proposed by an agent gets an `Agent` label, and is paused by default. Review the proposed filters, and press the `Play` icon to apply a proposed filter. Alternately, you can edit the filter before applying it, or delete the filter.

#### Review Agent Actions

There are two ways to access the **Agent Actions** UI where you can see details about all agent activity:

1. Expand `More` in the app's main sidebar and select **Agent Actions**.
2. Go to the **Logs** menu, and select **Agent Actions**.

The Agent Actions UI provides three lists:

- Pending destructive actions that are waiting your approval
- A summary of applied changes for your review, which you can choose to accept or revert
- A history of activity and your choices about reviewed and pending activity

## Enable the Agent Server

To enable the Agent Server:

1. Go to the **Issuenator** menu, select **Settings**, and go to the **Agent Server** tab.
2. Optional: you can change the proposed port, if the default port is busy on your machine.
2. Toggle the "Enable agent server" to on.
3. Optional: toggle "Allow agent writes" to let an agent perform actions on your behalf. Without this toggle enabled, the agent can still list issues and get incoming details through read-only Issuenator tools, but cannot make any changes to your local data.

The Agent Server only runs when the Issuenator app is open. 

## Connect your agent

The first time you enable the Agent Server, you must register the MCP tools with your preferred agent.

Whenever you close the Issuenator app, the MCP tools disconnect and you may need to reconnect them when you open the app again.

### Add the MCP server

When you enable the Agent Server, the Issuenator app writes the authentication token to your macOS Keychain.

You can use the supplied command to register the Issuenator Agent Server with Claude Code, or use your own agent's MCP registration process to register with a different agent.

#### Install with Claude Code

Run register commands from your terminal, not a running agent session. Pasting the command risks your agent deciding to run it, which can write the authentication token into the agent session and send it to your agent provider's API. This exposes your authentication token; if you paste it into your agent session, you should use the `Regenerate Token` button to rotate the token.

After you register the server, use your preferred harness to connect to the MCP tools. In Claude Code, type `/mcp` into a Claude Code session and select `issuenator` from the MCP servers listed there.

##### Install globally

If you want the Issuenator MCP tools to be available in a Claude Code session you start from anywhere on your filesystem, install the MCP at the user level.

Paste the following command. Replace the `<PORT>` in the command below with the port where your Agent Server is running:

```bash
claude mcp add --transport http issuenator http://127.0.0.1:<PORT>/mcp --header "Authorization: Bearer $(security find-generic-password -s Issuenator-agent-token -a mcp -w)" --scope user
```

The `--scope user` flag makes it available globally.

##### Install in a project

If you only want to use the Issuenator MCP tools when you're in a specific project:

1. Use `cd` to enter the project directory in your terminal.
2. Paste the following command. Replace the `<PORT>` in the command below with the port where your Agent Server is running:

```bash
claude mcp add --transport http issuenator http://127.0.0.1:<PORT>/mcp --header "Authorization: Bearer $(security find-generic-password -s Issuenator-agent-token -a mcp -w)"
```

### Reconnect after closing the app

The Agent Server only runs when the Issuenator app is running. Harnesses may see the MCP server tools as disconnected when you close the app, and you may need to reconnect again after you re-open the Issuenator app.

In Claude Code, type `/mcp` into the Claude session and select `issuenator` from the MCP servers listed there.

## Rotate an Agent Server token

If you have pasted your agent server token into your agent's running session, or if you rotate tokens regularly, you can generate a new token for the Issuenator MCP server.

To rotate an Issuenator Agent Server token:

1. Go to the **Issuenator** menu, select **Settings**, and go to the **Agent Server** tab.
2. Press the `Regenerate Token` button.
3. Remove the MCP server from your preferred harness. In Claude Code, the command is `claude mcp remove issuenator`
4. Add the MCP server again using the supplied command. For example, `claude mcp add` with the full string provided above.
5. Reconnect the MCP tools from your running agent session. In Claude Code, type `/mcp` into the Claude session and select `issuenator` from the MCP servers listed there.
