---
name: explorations
description: >
  Browse Futures Platform foresight explorations via FP MCP. Use when the user
  asks to search or pick an exploration, or before drivers, scenarios, or
  executive-summaries (those need an exploration_id).
metadata:
  version: "0.1.0"
  mcp_server: fp-mcp
  mcp_tool: list-explorations
---

# Explorations

Read-only access to **foresight explorations** in the user’s organisations through **FP MCP** (`fp-mcp`).

An **exploration** frames a futures question: topic, aim, focus area, geographic scope, audience, time range, and organisation. Results are **newest first**.

## When to use

- User asks what explorations exist, wants to search by name/topic, or needs an **exploration id**.
- Starting any workflow that needs **`exploration_id`** for drivers, scenarios, or executive summaries.
- User mentions Synapse explorations, futures projects, or org foresight work.

## Prerequisites

- **FP MCP** connected (`/mcp`, **`fp-mcp`**).
- **`FP_MCP_BEARER_TOKEN`** set in Plugins → Configure → Synapse.

## Tool

Call the **`list-explorations`** tool on **`fp-mcp`**.

## Parameters

| Parameter | Type | Default | Notes |
| --------- | ---- | ------- | ----- |
| `search` | string | — | Filter: name or topic contains this text. |
| `page` | integer | 1 | Page number, ≥ 1. |
| `per_page` | integer | 15 | 1–50 results per page. |

## Workflow

1. Call with `search` if the user named a topic; otherwise fetch the first page.
2. If `last_page` > `page`, fetch additional pages until you have enough rows or the user’s match.
3. Return **id**, title/topic, and framing fields the user cares about; keep ids for follow-up tools.
4. Pass **`exploration_id`** to drivers, scenarios, or executive-summaries skills as needed.

## Output

Present a compact table or numbered list: **id**, name/topic, time range, organisation (if returned). Offer to open drivers, scenarios, or executive summary for one id.

## Errors

| Issue | Action |
| ----- | ------ |
| 401 / 403 | Refresh bearer token; reconnect **`fp-mcp`**. |
| Empty results | Broaden `search` or confirm org access with the user. |
