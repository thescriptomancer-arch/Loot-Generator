# Loot-Generator (clean v0)

Purpose: a transparent, source-first D&D 3.5e loot data set. Each book harvest lives under `/sources/<BOOK>/...`, validated by simple JSON schemas in `/schemas`. The `/engine` folder indexes what to load. The `/dist` folder is where you (or another tool) can compile/aggregate outputs.

**This v0 includes:**
- PHB Armor & Shields (Table 7–6)
- PHB Adventuring Gear (Table 7–8 subset)
- PHB Tools & Skill Kits
- PHB Special Substances & Items
- PHB rule: Armor for Unusual Creatures (size/cost/weight scaling; masterwork armor)

**Incoming next (drop-in ready):**
- PHB Weapons (Table 7–5) → `/sources/PHB/items/weapons/weapons.core.json`
- PHB Spells → `/sources/PHB/spells/spells.index.json`

## How to use

1. Validate files (optional):
   - Each `*.core.json` under `items/...` follows `/schemas/table.v1.json`.
   - Each rule JSON under `rules/` follows `/schemas/rule.v1.json`.

2. Load order:
   - Read `/engine/harvest_index.json` to see the exact files to ingest.
   - Your generator should:
     - Load rules first (`rules/*`).
     - Load items tables next (`items/*/*/*.json`).

3. No code is required in this repo—just data and structure. You can build your own aggregator or have another tool read the files listed in `engine/harvest_index.json`.
