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
