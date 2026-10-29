# Synapse

<img src="assets/logo.png" width="96" alt="Futures Platform logo" />

Connect to the **Futures Platform Synapse** app through **FP MCP** (`fp-mcp`).

## What's included

- **FP MCP**: HTTP MCP with a configurable URL and bearer token ([`mcp.json`](mcp.json))
- **Skills**: FP MCP tool skills (`explorations`, `drivers`, `scenarios`, `executive-summaries`, `phenomena`) plus foresight workflows (`foresight-analyst`, `foresight-horizon-scanner`, `radar-creator`)

## Configure

In **Plugins → Configure → Synapse**, set:

| Setting | Variable | Required |
| -------- | -------- | -------- |
| FP MCP URL | `FP_MCP_URL` | No (defaults to staging) |
| FP MCP auth scheme | `FP_MCP_AUTH_SCHEME` | No (defaults to `Bearer`) |
| FP MCP bearer token | `FP_MCP_BEARER_TOKEN` | Yes |

[`mcp.json`](mcp.json) sends `Authorization: ${FP_MCP_AUTH_SCHEME} ${FP_MCP_BEARER_TOKEN}`.

Default URL: `https://api-staging.futuresplatform.com/mcp`

## Install (Claude Code)

From the marketplace root (this repo):

```text
/plugin marketplace add "/Users/natnael/claude plugin "
/plugin install synapse@futures-platform
/mcp
```

## Development

```text
claude plugin validate "/Users/natnael/claude plugin /plugins/synapse"
claude plugin validate "/Users/natnael/claude plugin /.claude-plugin/marketplace.json"
```
