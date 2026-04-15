# Colosseum Resources

AI agent skill for Solana hackathon builders. The advisor reads Colosseum's published hackathon resource index and recommends sponsor tools, SDKs, RPC providers, and build paths for a builder's specific project.

## Install

```bash
npx skills add ColosseumOrg/colosseum-resources
```

Sponsor-specific skills live in the source-of-truth resource repo and are installed from there:

```bash
npx skills add ColosseumOrg/hackathon-resources --skill phantom
npx skills add ColosseumOrg/hackathon-resources --skill arcium
```

## Skill

- `colosseum-resources` -- advisor that fetches the current Colosseum hackathon resource corpus.

This repo intentionally does not duplicate sponsor skill content. Sponsor skills are maintained in `ColosseumOrg/hackathon-resources`, the same repo that publishes the resource data consumed by this advisor.

## Contributing

Resource data and sponsor skill contributions belong in `ColosseumOrg/hackathon-resources`.

See https://github.com/ColosseumOrg/hackathon-resources/blob/main/CONTRIBUTING.md.
