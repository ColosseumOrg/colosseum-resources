---
name: phantom-connect
description: |
  Build user-facing dApps with Phantom wallet connection, embedded wallets, onboarding, and transaction
  flows. Use when building a user-facing web or mobile app, whether the builder is a developer or a
  coding agent.
license: MIT
metadata: {"category":"wallet","author":"phantom","tags":"solana,wallet,dapp,embedded-wallet,react,react-native,browser-sdk,phantom"}
---

# Phantom Connect

Phantom Connect is for builders creating user-facing dApps.

Use it when the primary product surface is a user-facing web or mobile app that needs onboarding, wallet
connection, transaction signing, or embedded wallet creation for 20M+ Phantom users.

## Choose This Skill When

- You are a developer or coding agent building a user-facing product
- The app needs embedded wallet onboarding or existing Phantom wallet connection
- You need wallet UX inside a React, React Native, or browser app
- Users should stay inside your app while using Phantom wallet infrastructure

## Use Another Phantom Skill When

- You are giving an agent a wallet for onchain actions: use `phantom-mcp-server`
- You need payments, payouts, or premium actions in a stablecoin: use `phantom-cash`
- You are building both an app and an agent layer: pair this skill with `phantom-mcp-server`

## Available SDKs

- React SDK for React web apps
- Browser SDK for vanilla JS/TS and non-React frameworks
- React Native SDK for iOS and Android apps

These SDKs support both embedded wallets and existing Phantom connection paths where available.

## Docs MCP Server For Development

Use the docs MCP server when your coding agent needs live Phantom Connect documentation while building:

```json
{
  "mcpServers": {
    "phantom-connect-sdk": {
      "type": "sse",
      "url": "https://docs.phantom.com/mcp"
    }
  }
}
```

This is a documentation server for builders. It is not the wallet MCP product that agents use for live
wallet actions.

## Common Prompts

```text
> How do I initialize the React SDK and connect a wallet?
> Show me how to initialize the Browser SDK
> How do I sign and send a Solana transaction from React Native?
```

## Key Implementation Rules

- For embedded wallets, use `signAndSendTransaction`; `signTransaction` and `signAllTransactions` are not supported
- Use `LAMPORTS_PER_SOL` instead of hardcoding lamport conversion values
- React Native: `import 'react-native-get-random-values'` must be the first import
- Browser SDK: initialize a `BrowserSDK` instance with the providers, address types, and `appId` your app needs
- Phantom Connect supports Solana Mainnet, Devnet, and Testnet

## Common Build Pattern

Use this split of responsibilities:

- Your app owns product UX
- Phantom Connect owns wallet onboarding, auth, and signing flows
- Your product owns business logic while Phantom Connect owns wallet infrastructure

Typical examples:

- A consumer trading app with embedded wallets
- A mobile app that needs Phantom-powered auth and signing
- A dApp that should feel native to existing Phantom users

## Build Guidance

- Start here when you are building a user-facing dApp
- Reach for `phantom-mcp-server` only when the product also includes an agent that needs its own wallet
- Pair with `phantom-cash` when the app needs stablecoin checkout, payouts, or paid actions
- If the docs MCP server is unavailable, fall back to [docs.phantom.com](https://docs.phantom.com)

## References

- [Phantom Connect marketing site](https://phantom.com/connect)
- [Phantom developer docs](https://docs.phantom.com)
- [Wallet SDK overview](https://docs.phantom.com/wallet-sdks-overview)
- [React SDK](https://docs.phantom.com/sdks/react-sdk)
- [Browser SDK](https://docs.phantom.com/sdks/browser-sdk)
- [React Native SDK](https://docs.phantom.com/sdks/react-native-sdk)
- [Phantom Connect docs MCP server](https://docs.phantom.com/resources/mcp-server)
