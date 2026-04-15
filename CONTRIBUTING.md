# Contributing

Colosseum Resources publishes the advisor skill that helps hackathon builders navigate sponsor tools and curated Solana resources.

The source of truth for resource data and sponsor skills is `ColosseumOrg/hackathon-resources`. This repository intentionally contains only the `colosseum-resources` advisor skill.

## Add a Sponsor

1. Add `sponsors/<slug>.md` in `ColosseumOrg/hackathon-resources`.
2. Add the sponsor entry to `manifest.json`.
3. Include accurate links, tags, and accent color.
4. Open a PR against `hackathon-resources`.
5. Confirm the GitHub Pages publish workflow updates `current.json`.

## Add a Sponsor Skill

1. Create `skills/<slug>/SKILL.md` in `ColosseumOrg/hackathon-resources`.
2. Keep the skill focused on agent-actionable guidance, not marketing copy.
3. Add references, examples, or MCP config only when the `SKILL.md` depends on them.
4. Validate the skill in `hackathon-resources`.
5. Confirm it is installable with:

```bash
npx skills add ColosseumOrg/hackathon-resources --skill <slug>
```

## Add Curated Resources

1. Add or update a JSON file in `ColosseumOrg/hackathon-resources/resources/`.
2. Reference the resource key from the active hackathon in `manifest.json`.
3. Keep links stable and public.
4. Confirm the GitHub Pages JSON includes the new section after the publish workflow runs.

## Deprecation

- To remove a sponsor, add `"deprecated": true` to the manifest entry first.
- Do not rename slugs in place. Add a new entry and deprecate the old slug.
- Keep old skill folders in `hackathon-resources` only when existing install commands still need to resolve.

## Example PR Flow

1. Submit the resource data change to `hackathon-resources`.
2. Wait for the GitHub Pages publish workflow to update `current.json`.
3. If a sponsor skill changed, validate and publish it from `hackathon-resources`.
4. Update this advisor only if recommendation behavior or install-command copy changes.
5. Open a PR explaining the source resource data PR and any advisor changes.
