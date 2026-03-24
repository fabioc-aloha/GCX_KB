# Instructions

> Reusable auto-loaded instruction files for any GCX repo

## Contents

Standalone `.instructions.md` files that can be adopted into any heir repo's `.github/instructions/` folder.

## Requirements

- Must have `description` in YAML frontmatter
- Should have `applyTo` glob for automatic loading
- Must be self-contained (no external dependencies)

## Adopting an Instruction

1. Copy the `.instructions.md` file to your repo's `.github/instructions/`
2. Verify the `applyTo` glob matches your file patterns
3. Test that it auto-loads when editing matching files
