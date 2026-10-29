---
name: drivers
description: >
  Read drivers of change for a Futures Platform exploration via FP MCP. Use when
  the user asks for scenario axes, forces shaping the future, or recommended
  drivers for 2x2 scenarios; requires exploration_id from explorations.
metadata:
  version: "0.1.0"
  mcp_server: fp-mcp
  mcp_tool: list-drivers
---

# Drivers

Read-only access to **drivers of change** through **FP MCP** (`fp-mcp`).

A **driver** is a force that shapes the future of an exploration topic (markdown description). Drivers are the **axes of 2×2 scenarios**. Only drivers from explorations in the user’s organisations are returned.

## When to use

- User asks for drivers, scenario axes, or forces of change for an exploration.
- User wants **recommended** drivers (agent-suggested scenario axes) vs other drivers.
- Building or explaining scenarios after an exploration is chosen.

## Prerequisites

- **`exploration_id`** from the **explorations** skill (short hash id).
- **FP MCP** connected with valid bearer token.

## Tool

Call the **`list-drivers`** tool on **`fp-mcp`**.

## Parameters

| Parameter | Type | Default | Notes |
| --------- | ---- | ------- | ----- |
| `exploration_id` | string | — | Limit to one exploration (preferred when user named one). |
| `search` | string | — | Driver name contains this text. |
| `recommended` | boolean | — | `true` = agent-recommended scenario axes only; `false` = non-recommended only. |
| `page` | integer | 1 | Page number, ≥ 1. |
| `per_page` | integer | 15 | 1–50 per page. |

## Workflow

1. If no **`exploration_id`**, use **explorations** first and confirm with the user.
2. Call **`list-drivers`** with `exploration_id` and optional `search` / `recommended`.
3. Paginate while `page` < `last_page` if the user needs a full set.
4. Summarize each driver: id/name, whether recommended, and the description gist.
5. For scenario detail, follow with **scenarios** on the same **`exploration_id`**.

## Output

Numbered list with driver names and short excerpts from descriptions. Note which drivers are recommended axes when filtering.

## Errors

| Issue | Action |
| ----- | ------ |
| Missing exploration id | **explorations**, then retry. |
| Empty drivers | Check id, `search`, or `recommended` filter. |
