---
name: executive-summaries
description: >
  Read executive summaries (final exploration write-ups) via FP MCP. Use when
  the user asks for the executive summary, final report, or synthesis of an
  exploration; requires exploration_id from explorations.
metadata:
  version: "0.1.0"
  mcp_server: fp-mcp
  mcp_tool: list-executive-summaries
---

# Executive summaries

Read-only access to **executive summaries** through **FP MCP** (`fp-mcp`).

An **executive summary** is the **final markdown write-up** of an exploration, based on its drivers and scenarios. Only summaries for explorations in the user’s organisations are returned, and **only once they have content**. Results are **newest first**.

## When to use

- User asks for the executive summary, final narrative, or leadership-ready synthesis of an exploration.
- User wants the “answer” or conclusion after drivers and scenarios were explored elsewhere.
- Delivering a brief for decision-makers from Synapse content.

## Prerequisites

- **`exploration_id`** from **explorations** when scoped to one exploration.
- **FP MCP** connected with valid bearer token.

## Tool

Call the **`list-executive-summaries`** tool on **`fp-mcp`**.

## Parameters

| Parameter | Type | Default | Notes |
| --------- | ---- | ------- | ----- |
| `exploration_id` | string | — | Single exploration’s summary. |
| `search` | string | — | Title contains this text. |
| `page` | integer | 1 | Page number, ≥ 1. |
| `per_page` | integer | 15 | 1–50 per page. |

## Workflow

1. If the user named an exploration, set **`exploration_id`**; otherwise fetch recent summaries across explorations.
2. Paginate if browsing many summaries.
3. Render markdown summary faithfully; add a short plain-language lead-in for executives if helpful.
4. If empty for an exploration, tell the user the summary may not be published yet; offer **scenarios** or **drivers** instead.

## Output

Title, exploration link/id, and the summary body (or an excerpt plus “show full text” on request).

## Errors

| Issue | Action |
| ----- | ------ |
| Empty for one exploration | Summary not ready or no access; verify id. |
| Auth errors | Refresh **`FP_MCP_BEARER_TOKEN`**. |
