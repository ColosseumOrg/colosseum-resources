---
name: phantom-mcp-server
description: |
  Give your agent a wallet that syncs with the user's Phantom account.
  Use when an agent needs a wallet solution for balances, transfers, swaps with no fees, signatures, or other
  onchain actions through Phantom, or when building agent skills, tools, and MCP servers that rely on it.
license: MIT
metadata: {"category":"wallet","author":"phantom","tags":"solana,evm,bitcoin,wallet,mcp,agents,phantom,onchain"}
---

# Phantom MCP Server

Phantom MCP server gives your agent a wallet that syncs with the user's Phantom account.

Use it when an agent needs to check balances, sign messages, send tokens, swap assets, or execute other
wallet actions through Phantom, or when you are building skills, tools, services, or interfaces that
rely on it.

## Choose This Skill When

- You are an agent that needs a wallet and user-approved onchain actions through Phantom
- You are a developer building a skill, tool, service, or interface that agents use through Phantom MCP server
- The product needs balances, transfers, swaps with no fees, signatures, or other wallet actions through Phantom
- Your product owns protocol logic while Phantom MCP server owns wallet execution

## Use Another Phantom Skill When

- You are building a user-facing app with onboarding and wallet connection: use `phantom-connect`
- You need stablecoin payments, payouts, or paid agent actions: use `phantom-cash`
- You need both wallet execution and payments: pair this skill with `phantom-cash`

## Setup [REQUIRED]

### 1. Get an App ID

Register at [phantom.com/portal](https://phantom.com/portal) and copy your `appId`.

### 2. Add the server to your MCP config

```json
{
  "mcpServers": {
    "phantom-mcp": {
      "command": "npx",
      "args": ["-y", "@phantom/mcp-server"],
      "env": { "PHANTOM_APP_ID": "YOUR_APP_ID" }
    }
  }
}
```

Use the same server shape in Claude Code, Cursor, Windsurf, or any client that supports stdio MCP
servers.

### 3. Authenticate

On first run, `phantom-mcp` opens a browser for OAuth. Sessions persist across restarts. If an auth
error appears later, re-run the sign-in flow and retry.

`phantom-mcp` connects to mainnet. Use a dedicated test wallet with minimal funds for development.

### 4. Preflight check

Before any wallet action, confirm the user is connected:

```text
> What's my wallet address?
```

Expected result: `get_wallet_addresses` returns one or more addresses. If it fails with auth errors,
restore the session before continuing.

## Operational Rule

Before any wallet action, call `get_wallet_addresses` or `get_connection_status` to confirm auth.

## What Agents Can Do

- Check wallet addresses and connection state
- Read token balances with current USD pricing
- Transfer native and token balances
- Route and execute swaps with no fees
- Sign messages
- Sign and broadcast prepared transactions

## Common Build Pattern

Use this split of responsibilities:

- Your skill or service handles protocol-specific logic
- Phantom MCP server handles wallet execution
- The agent orchestrates both in one workflow

Typical examples:

- A DeFi copilot that finds a position and then asks Phantom to execute
- A treasury agent that checks balances, then transfers funds after policy checks
- A commerce agent that verifies payment state and then settles onchain actions

## Common Prompts

```text
> What tokens do I have?
> Swap 10 USDC to SOL
> Send 0.001 SOL to <address>
> Sign this message to verify account ownership
```

## Supported Chains

`phantom-mcp` supports Solana, Ethereum, Base, Polygon, Arbitrum, and Bitcoin.

Solana is the primary chain for most Phantom agent flows and the default place to start for Colosseum
builders.

## Build Guidance

- Start here for agent-track projects
- Keep wallet execution in Phantom and domain logic in your own skill or service
- Treat OAuth and wallet connectivity as required preflight, not optional cleanup
- Pair with `phantom-cash` when the agent needs stable pricing, payouts, or paid actions

## References

- [Phantom MCP Server docs](https://docs.phantom.com/resources/phantom-mcp-server)
- [Phantom developer portal](https://phantom.com/portal)
- [AI development tools](https://docs.phantom.com/developer-powertools/ai-tools)
