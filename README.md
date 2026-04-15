# Colosseum Resources

AI agent skills for Solana hackathon builders. The main advisor skill reads Colosseum's published hackathon resource index and recommends sponsor tools, SDKs, RPC providers, and build paths for a builder's specific project.

## Install

```bash
npx skills add ColosseumOrg/colosseum-resources
```

Install a sponsor-specific skill:

```bash
npx skills add ColosseumOrg/colosseum-resources --skill phantom
npx skills add ColosseumOrg/colosseum-resources --skill arcium
```

## Skills

- `colosseum-resources` -- advisor that fetches the current Colosseum hackathon resource corpus.
- `phantom` -- routes builders to the right Phantom product skill.
- `phantom-connect` -- Phantom Connect and embedded wallet guidance.
- `phantom-cash` -- Phantom CASH payment guidance.
- `phantom-mcp-server` -- Phantom MCP Server guidance for agents.
- `arcium` -- privacy-preserving Solana app guidance with Arcium MPC.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).
