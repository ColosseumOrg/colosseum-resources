# Colosseum Resources

AI agent skill for Solana hackathon builders. The advisor reads Colosseum's published hackathon resource index and recommends sponsor tools, SDKs, RPC providers, and build paths for a builder's specific project.

## Install

```bash
npx skills add ColosseumOrg/colosseum-resources
```

Sponsor-specific skills live in sponsor-owned repositories and are installed from the command published in the live resource data:

```bash
npx skills add arcium-hq/agent-skills
```

## Skill

- `colosseum-resources` -- advisor that fetches the current Colosseum hackathon resource corpus.

This repo intentionally does not duplicate sponsor skill content. Sponsor skills are maintained in sponsor-owned GitHub repositories. `ColosseumOrg/hackathon-resources` publishes the resource data consumed by this advisor, including each sponsor skill repository URL and install command when available.

## Contributing

Resource data contributions belong in `ColosseumOrg/hackathon-resources`. Sponsor skill content belongs in the sponsor's own GitHub repository.

See https://github.com/ColosseumOrg/hackathon-resources/blob/main/CONTRIBUTING.md.
