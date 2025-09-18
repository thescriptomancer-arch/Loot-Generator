# Loot-Generator Repo Audit
_Timestamp: 2025-09-18T17:51:22.543057Z_

## Summary
- Manifest status: missing
- Files before fixes: 35 files

## Changes Applied
- Replaced `config/hopper_manifest.json` to align output paths with existing filenames.
- Replaced/created `rules/PHB/extraction_rules.json` with stubs for weapons, armor/shields, spells.
- Added schemas: `schemas/weapon.json`, `schemas/armor_shield.json`, `schemas/spell.json`.
- Ensured missing data files exist (created stubs if absent):
  - data/PHB/items/weapons.phb.json
  - data/PHB/items/armor_shields.phb.json
  - data/PHB/spells/spells.phb.json

## Outstanding Issues
- PHB PDF missing at books/PHB/Player's Handbook. Core Rulebook I v.3.5.pdf
- Missing expected output file: data/PHB/equipment/adventuring_gear.json
- Missing expected output file: data/PHB/equipment/special_substances_and_items.json
- Missing expected output file: data/PHB/equipment/tools_and_skill_kits.json
- Missing expected output file: data/PHB/armor/armor_unusual_sizes.json

## Next Data Tasks (Harvest)
- Populate `data/PHB/items/weapons.phb.json` with all PHB weapons rows.
- Populate `data/PHB/items/armor_shields.phb.json` with all PHB armor/shield rows.
- Populate `data/PHB/spells/spells.phb.json` with PHB spells (levels, components, etc.).
