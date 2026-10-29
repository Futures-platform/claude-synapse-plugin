---
name: scenarios
description: >
  Read 2x2 futures scenarios for a Futures Platform exploration via FP MCP. Use
  when the user asks for scenarios, quadrant futures, narratives, indicators, or
  development paths for an exploration; requires exploration_id from explorations.
metadata:
  version: "0.1.0"
  mcp_server: fp-mcp
  mcp_tool: list-scenarios
---

# Scenarios

Read-only access to **2×2 scenario sets** through **FP MCP** (`fp-mcp`).

A **scenario set** crosses two drivers (x and y axis) into **four scenarios**. Each scenario can include title, axis drivers and states, time range, summary, content, narrative, indicators, key actors, and development path. Only scenarios from the user’s organisations are returned.

## When to use

- User asks for scenarios, alternative futures, or quadrant narratives for an exploration.
- User needs indicators, actors, or development paths from Synapse scenarios.
- After **drivers**, to read the full scenario content tied to those axes.

## Prerequisites

- **`exploration_id`** from **explorations**.
- **FP MCP** connected with valid bearer token.

## Tool

Call the **`list-scenarios`** tool on **`fp-mcp`**.

## Parameters

| Parameter | Type | Default | Notes |
| --------- | ---- | ------- | ----- |
| `exploration_id` | string | — | Limit to one exploration. |
| `search` | string | — | Scenario title contains this text. |
| `page` | integer | 1 | Page number, ≥ 1. |
| `per_page` | integer | 15 | 1–50; payloads are large—prefer smaller pages unless the user needs everything. |

## Workflow

1. Resolve **`exploration_id`** via **explorations** if missing.
2. Optionally **drivers** first so axis names are familiar when reading scenarios.
3. Call **`list-scenarios`** with `exploration_id`; add `search` if the user named one scenario.
4. Paginate only as needed; summarize long fields unless the user asked for full text.
5. For the written conclusion of the exploration, use **executive-summaries**.

## Output

For each scenario: title, axis drivers/states, time range, summary, and (on request) narrative, indicators, actors, or development path. Compare quadrants when the user wants strategic implications.

## Errors

| Issue | Action |
| ----- | ------ |
| Missing exploration id | **explorations**, then retry. |
| Timeouts / huge responses | Lower `per_page`; fetch one scenario at a time with `search`. |
