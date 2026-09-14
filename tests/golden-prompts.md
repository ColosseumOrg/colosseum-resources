# Golden Prompts

Use these scenarios for human-evaluated forward checks after installing the skill. Evaluate recommendations against the fetched payload at test time; resource names can change as the corpus is updated.

## Pass Criteria

- The agent fetches the current resource index before making corpus-based recommendations.
- It selects an ecosystem before recommending tools and uses only that track's entries.
- It preserves source links, caveats, offers, and sponsor skill commands exactly enough to avoid changing their meaning or eligibility.
- It reports missing or empty coverage rather than borrowing entries from another track.
- It does not imply cross-ecosystem compatibility that the selected track does not establish.
- It recommends a small project-specific set and explains why each item fits, rather than listing the corpus.

## Behavioral Cases

| Case | Prompt | Expected behavior |
| --- | --- | --- |
| Ecosystem required | "I'm building a mobile rewards wallet. What should I use?" | Lists ecosystem names from `tracks` and asks the builder to select one. Makes no tool recommendation yet. |
| Solana isolation | "I'm building a mobile rewards wallet on Solana." | Uses only the `solana` track. It may recommend current Solana sponsor, mobile, or RPC entries when they fit, with links and caveats from that track. |
| Ethereum isolation | "I'm building a TypeScript smart-contract app on Ethereum." | Uses only the `ethereum` track. It does not recommend Phantom, Helius, or any other Solana-only entry. It reports empty Ethereum sponsor or RPC arrays honestly if they remain empty. |
| Hyperliquid route | "I'm building a Hyperliquid trading bot with real-time market data and signed orders." | Chooses current `hyperliquid` data, action, signing, precision, and stream resources; does not treat a Solana RPC provider as Hyperliquid infrastructure. |
| Base consumer app | "I'm building a Base checkout flow inside a Farcaster Mini App." | Uses current `base` checkout and Mini App resources only, preserving any wallet or payment caveats in those entries. |
| Zcash privacy wallet | "I'm building a native iOS shielded wallet on Zcash." | Uses current `zcash` address/payment and native SDK resources. It does not substitute Solana privacy tooling. |
| Track comparison | "Compare the current contract development paths for Ethereum and Arbitrum." | Keeps two track-specific sections, uses each track independently, and does not pool resources or claim compatibility without supporting data. |
| Missing track | "What should I use to build on an ecosystem that is not in this index?" | Shows available tracks and states that the corpus has no dedicated coverage. It does not fall back to Solana resources. |
| Empty selected bundle | "Recommend an RPC provider for Ethereum from the current Colosseum corpus." | If `ethereum.rpcProviders` is empty, says none is listed and does not use the top-level or Solana provider array. |
| Fetch failure | "Recommend sponsor offers for my Base project." | If the index cannot be fetched, reports that failure and makes no claims about sponsors, offers, links, or install commands. |

## Legacy Payload Cases

These cases use a fixture with no non-empty `tracks` array and a populated top-level resource bundle.

| Case | Prompt | Expected behavior |
| --- | --- | --- |
| Legacy Solana | "Recommend resources for a Solana payments app." | Treats the top-level bundle as Solana and uses its entries normally. |
| Legacy non-Solana | "Recommend resources for a Base payments app." | States that the legacy payload has no Base track coverage and does not use any top-level entry. |
