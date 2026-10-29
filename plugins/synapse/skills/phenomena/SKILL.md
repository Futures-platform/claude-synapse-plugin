---
name: phenomena
description: >
  Search the Futures Platform phenomena library via FP MCP. Use when the user
  asks for weak signals, trends, wild cards, phenomena, or horizon-scanning
  library hits; supports search, types filter, and lookup by ids.
metadata:
  version: "0.1.0"
  mcp_server: fp-mcp
  mcp_tool: list-phenomena
---

# Phenomena

Read-only search of the **Futures Platform phenomena library** through **FP MCP** (`fp-mcp`).

A **phenomenon** is a change in the world (weak signal, strengthening, established, weakening, wild card, summary, etc.) with title, summary, body, time range, and related phenomena. The library is **shared across all organisations**.

## When to use

- User asks to search phenomena, signals, trends, or wild cards in the FP library.
- **`foresight-horizon-scanner`** library checks and update finds (required path for all **`list-phenomena`** calls in that workflow).
- **`radar-creator`** or **`foresight-analyst`** need library ids or source material.
- User provides phenomenon **ids** (or ids from `related_phenomena`) to fetch specific entries.

## Prerequisites

- **FP MCP** connected with valid bearer token.

## Tool

Call the **`list-phenomena`** tool on **`fp-mcp`**.

## Parameters

| Parameter | Type | Default | Notes |
| --------- | ---- | ------- | ----- |
| `search` | string | — | **≥ 2 characters**; required unless `ids` is set. Title matches rank first, then short title and summary. |
| `types` | string[] | — | Filter: `weaksignal`, `rising`, `established`, `cooling`, `wildcard`, `summary`, `undefined`. |
| `ids` | string[] | — | Fetch specific phenomena by id. |
| `sort` | string | relevance | `created_at` or `updated_at` (omit for relevance). |
| `order` | string | asc | `asc` or `desc`; used with `sort`. |
| `per_page` | integer | 10 | Max **10**; **no further pages**—narrow searches to find more. |

## Workflow

1. Prefer **many narrow searches** (1–3 word terms) over one broad query; each call returns at most 10 hits.
2. Use `types` when the user names a signal class (e.g. wild cards → `wildcard`).
3. Use `ids` to expand **`related_phenomena`** or to reload a known entry.
4. Deduplicate by id when running multiple searches (see **`radar-creator`** for radar-scale collection).
5. Cite **title** and **id** when recommending phenomena to the user.

## Output

Compact list: id, title, type/status, time range, summary line; include body only when the user needs depth.

## Errors

| Issue | Action |
| ----- | ------ |
| Validation on `search` | Use ≥ 2 chars or pass `ids`. |
| Too few hits | Rephrase search; run additional targeted queries. |
| Tool missing | Token may not include this tool; check with admin. |
