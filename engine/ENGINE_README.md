# Engine Notes

This directory only declares *what to load* and in which order. Your generator should:

1) Load rules first (they inform later transforms).
2) Load item tables next (equipment, armor/shields, ammunition, etc.).
3) Derive or join extra fields at compile time (e.g., apply size scaling from rules to armor).

No executable code here—purely declarative indexing.

## Validation

- `schemas/table.v1.json` and `schemas/rule.v1.json` are intentionally simple.
- You can ignore unknown fields; add more later without breaking clients.

## Size/shape rules (PHB highlights included)

- Armor sizing and masterwork behavior are encoded in `sources/PHB/rules/armor_for_unusual_creatures.json`.
- Armor & shields core statistics come from `sources/PHB/items/armor_shields/armor_shields.core.json`.
- Common gear and alchemical items are in `sources/PHB/items/equipment/...`.

## Extending

Add more books by creating a new folder under `/sources/<BOOK_CODE>/...` and appending a block to `/engine/harvest_index.json`. Keep per-book harvests self-contained.

## Roadmap (next drops)

- **PHB Weapons (Table 7–5)** → `sources/PHB/items/weapons/weapons.core.json`
- **PHB Spells index** (metadata for creation rules) → `sources/PHB/spells/spells.index.json`

Both files will use the same lightweight table schema (or a thin variant) and plug straight into the index.
