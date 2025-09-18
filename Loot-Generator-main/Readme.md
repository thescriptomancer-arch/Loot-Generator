# D&D 3.5e — Book-First Hopper (Zero-Assumption)

**Goal**: ingest whole books (PDF or text) and extract *all* item-relevant facts as generic, cited assertions.
No early categories (armor/weapons/materials), no forced price models. We store raw blocks, tables, and
atomic assertions with provenance. Later, we *project* into canonical schemas as needed.

### Layout
- `/books/<BOOK_ID>/` — per-book configs and (later) the raw dumps.
- `/pipelines/` — instructions for Lovable or any runner to perform segmentation & extraction.
- `/schemas/` — generic JSON Schemas for blocks, tables, assertions, entities, citations.
- `/data/raw/<BOOK_ID>/` — raw segmented blocks/tables (machine-generated).
- `/data/assertions/<BOOK_ID>/` — normalized atomic assertions (machine-generated).
- `/data/catalog/` — merged, de-duplicated cross-book catalogs (items, abilities, rules), still generic.
- `/config/` — global hopper config and merge policies.
- `/tests/` — smoke tests for harvest and merge.

### Workflow
1) Drop a book (PDF/Text) into your runner and execute `/pipelines/BOOK_HARVEST.txt`.
2) This produces raw blocks/tables and generic assertions under `/data/.../<BOOK_ID>/`.
3) Merge passes produce generic catalogs under `/data/catalog/`.
4) Only after we like the generic catalogs do we design domain schemas and project to canon.

**Pilot**: Start with PHB (no domains assumed). When ready, add DMG/DMG2/MIC—no structural changes needed.
