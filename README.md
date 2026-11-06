# AgentQuest Crafting Directory

Fork of the AgentQuest item and recipe catalog, with JSON examples, balance guidance, and catalog validation.

The main artifacts are the item, ingredient, and recipe JSON files under `world/crafting/`, plus the validation script. This is a data catalog for the upstream game ecosystem.

## Provenance

This repository is a fork of [xxiled-plastic-cat/agentquest-crafting-directory](https://github.com/xxiled-plastic-cat/agentquest-crafting-directory). Upstream authorship and license terms apply to the retained source. The fork may differ from the upstream default branch; inspect its commit history when reviewing a specific implementation.

## Explore the repository

- [`world/crafting/`](world/crafting/)
- [`scripts/`](scripts/)
- [`docs/`](docs/)
- [`examples/`](examples/)

## Project documentation

The existing guide below preserves the project-specific setup, examples, and credits. Its commands describe the checked-in project; no deployment or transaction is performed by reading this repository.

<details>
<summary>Read the project guide</summary>

![AgentQuest Banner](images/agentquest-banner.png)

# AgentQuest Crafting Directory

Community-maintained crafting catalog for Agent Quest.

This repository holds contributor-submitted craftable gear definitions and recipes.
Accepted content is reviewed, rebalanced if needed, and released as tagged catalog versions
for the private game repository to consume safely.

## Repository Layout

- `world/crafting/items.json`: canonical craftable items (`weapon` and `armor` only)
- `world/crafting/ingredients.json`: approved raw/simple crafting inputs
- `world/crafting/recipes.json`: recipes that produce craftable items
- `examples/example_weapon.json`: copy-ready balanced weapon example
- `examples/example_armor.json`: copy-ready balanced armor example
- `docs/CONTRIBUTING.md`: contribution flow, rules, and checklist
- `docs/BALANCE_GUIDE.md`: stat and design guidance
- `docs/DISCLAIMER.md`: rights, moderation, and attribution policy

## Contribution Flow

1. Read `docs/CONTRIBUTING.md` and `docs/BALANCE_GUIDE.md`.
2. Add one item entry in `items.json` and one matching recipe in `recipes.json`.
3. Ensure recipe ingredients reference existing IDs in `ingredients.json`.
4. Run local validation:

```bash
npm run validate:catalog
```

5. Open a pull request with your item and recipe.

## Validation

Automated validation checks:

- JSON structure and parse correctness
- object-key to `id` consistency for items and recipes
- required `lore` on items and `creator` on recipes
- recipe `outputItemId` and ingredient ID reference integrity
- allowed item categories (`weapon`, `armor`)
- rejection of processed metal-style ingredient IDs

Validation runs locally via `npm run validate:catalog` and in CI on pull requests.

</details>
