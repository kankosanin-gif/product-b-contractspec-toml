# ContractSpec (TOML) Guide

## Why TOML
- Easier for humans to read than nested JSON/YAML in long-lived ops docs
- Stable key-value structure fits contract-driven execution
- Good diff readability in Git history

## Required sections
- `[contract]`: id, owner, assignee, severity
- `[scope]`: in/out boundaries
- `[links]`: requirement/architecture/issue references
- `[[deliverables]]`: one entry per concrete output
- `[verification]`: commands + required evidence
- `[completion]`: objective done criteria
- `[gates]`: gate impact flags (G1..G5 mapping)
- `[report]`: output format constraints

## Validation rules (minimum)
1. `contract.id` must be present and unique
2. At least one deliverable required
3. At least one verification command required
4. `completion.criteria` cannot be empty
5. If `gates.security=true`, security checks list must be non-empty

## Suggested workflow
1. Create `CONTRACTSPEC_*.toml`
2. Attach to issue/PR
3. Execute task in isolated subagent run
4. Produce evidence bundle
5. Update gate decision log

## Future enhancement
- Add TOML validator script with strict schema checks
- Auto-generate execution ledger rows from ContractSpec TOML
