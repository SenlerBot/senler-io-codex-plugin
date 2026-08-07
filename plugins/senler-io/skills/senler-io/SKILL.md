---
name: senler-io
description: Use when working with the Senler.io MCP plugin/API, including inspecting projects, access members, channels, agents, dialogs, spaces, leads, analytics, billing, data sources, MCP servers, metrics, events, processes, documentation, API tokens, storage, or project variables through Senler.io. OAuth access is project-scoped.
---

# Senler.io MCP

Use the Senler.io MCP server for Senler.io API work.

## Safety

- Treat OAuth as project-scoped access for the Senler.io project selected during authorization.
- If Senler.io MCP tools are unavailable, say that OAuth connection is required and do not invent results from memory.
- Prefer read-only inspection before writes.
- Before destructive, billing-affecting, access-changing, token-changing, message-sending, or automation/process-changing actions, summarize the intended API action and get explicit confirmation.
- For bulk updates, test with a small sample first when the tools allow it.
- If available tools are unclear, search or inspect MCP tools before choosing an operation.

## Usage Notes

- Use Senler.io terminology in user-facing summaries: projects, members, access, channels, agents, dialogs, spaces, leads, data sources, MCP servers, metrics, events, processes, documentation, API tokens, storage, and project variables.
- Do not ask the user for OAuth tokens. The MCP server handles OAuth credentials.
- Do not pass hidden context such as project ID or authorization token unless the MCP tool explicitly asks for it. The server injects project context from OAuth when possible.
- Keep identifiers visible in summaries so the user can verify the target project, member, channel, lead, or object before a write.

## Connection and Project Context

- When the user asks about the current connection, call `show_connection` so Codex displays the interactive project card. Use `get_current_project` when a compact text-only check is more appropriate.
- Before a write, identify the current project with `get_current_project` when the project has not already been established in the conversation.
- If no credential is connected, use `connect_account` to start OAuth. Never ask the user to paste an OAuth token.
- Prefer the card buttons for switching projects or disconnecting. The switch button revokes the current MCP access and refresh tokens, then asks Codex to start OAuth again so the user can select another project.
- If interactive UI is unavailable, use the text fallback: confirm the user's intent, call `disconnect_account`, make a new protected Senler.io request to start OAuth, then verify with `get_current_project`.
- Do not tell the user to remove or reinstall the plugin merely to disconnect or switch projects.
- Never claim that switching succeeded until `get_current_project` reports the newly selected project.
