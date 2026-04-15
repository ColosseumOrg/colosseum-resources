# Golden Prompts

Use these prompts for human-evaluated spot checks after installing the skill.

Pass criteria for every prompt: the agent mentions at least two expected tools or resources and explains why they fit the project specifically. If it offers a sponsor skill command, the command must match the sponsor's `skillInstallCommand` from the live resource data. It must not invent a `ColosseumOrg/hackathon-resources --skill <slug>` command.

| Scenario | Prompt | Expected tools or resources |
| --- | --- | --- |
| Consumer wallet app | "I'm building a consumer mobile wallet app for rewards and simple swaps. What should I use?" | Phantom and one of Swig or MoonPay |
| DeFi trading bot | "I'm building a Solana DeFi trading bot with treasury controls and reliable execution." | Squads and an RPC provider |
| ZK privacy app | "I'm building a private sealed-bid auction app on Solana." | Arcium and an RPC provider |
| Mobile game | "I'm building a mobile game with Solana assets and wallet login." | Phantom and mobile build-path resources |
| DAO governance tool | "I'm building a DAO governance dashboard with treasury actions." | Squads and governance resources |
| Payment processing | "I'm building checkout and stablecoin payment flows for creators." | Swig or MoonPay, plus Phantom |
| NFT marketplace | "I'm building an NFT marketplace for game assets." | Metaplex and Phantom |
| Cross-chain bridge | "I'm building cross-chain bridge UX for Solana users." | Relevant infrastructure resources and an RPC provider |
| Social app with identity | "I'm building a social app where users prove identity and hold a Solana wallet." | World or Privy, plus a relevant build path |
| Developer tooling/SDK | "I'm building a developer SDK and CLI for Solana apps." | Relevant curated resources from foundations or build paths |
