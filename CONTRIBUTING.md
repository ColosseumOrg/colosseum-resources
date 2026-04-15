# Contributing

Colosseum Resources publishes agent skills that help hackathon builders navigate sponsor tools and curated Solana resources.

The source of truth for resource data is `ColosseumOrg/hackathon-resources`. This repository packages the installable skills.

## Add a Sponsor

1. Add `sponsors/<slug>.md` in `ColosseumOrg/hackathon-resources`.
2. Add the sponsor entry to `manifest.json`.
3. Include accurate links, tags, and accent color.
4. Open a PR against `hackathon-resources`.
5. After merge, copy any sponsor skill into this repo if it should be installable by agents.

## Add a Sponsor Skill

1. Create `skills/<slug>/SKILL.md` in `ColosseumOrg/hackathon-resources`.
2. Keep the skill focused on agent-actionable guidance, not marketing copy.
3. Add references, examples, or MCP config only when the `SKILL.md` depends on them.
4. Copy the final skill folder into this repo under `skills/<slug>/`.
5. Validate the copied skill before publishing this repo.

## Add Curated Resources

1. Add or update a JSON file in `ColosseumOrg/hackathon-resources/resources/`.
2. Reference the resource key from the active hackathon in `manifest.json`.
3. Keep links stable and public.
4. Confirm the GitHub Pages JSON includes the new section after the publish workflow runs.

## Deprecation

- To remove a sponsor, add `"deprecated": true` to the manifest entry first.
- Do not rename slugs in place. Add a new entry and deprecate the old slug.
- Keep old skill folders only when existing install commands still need to resolve.

## Example PR Flow

1. Submit the resource data change to `hackathon-resources`.
2. Wait for the GitHub Pages publish workflow to update `current.json`.
3. If a skill changed, copy the updated skill folder here.
4. Run validation for this repo.
5. Open a PR explaining the resource data PR and the copied skill changes.
