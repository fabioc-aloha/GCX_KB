# Contributing to GCX_KB

> How to check, adopt, and promote knowledge across GCX repos

## The Two Rules

1. **Check global first** -- Before creating any new skill, trifecta, instruction, prompt, or pattern in your local repo, search GCX_KB for existing content.
2. **Promote new work** -- If you create something reusable locally, contribute it back to GCX_KB so all heirs benefit.

## Workflow

### Checking for Existing Content

```
1. Clone/pull GCX_KB locally
2. Search by name, domain, or keyword
3. If found → adopt directly or adapt with local context
4. If not found → create locally, validate, then promote
```

### Promoting New Content

```
1. Validate locally -- the content must be tested and working in your repo
2. Generalize -- remove repo-specific paths or hardcoded values
3. Add README -- every trifecta needs an adoption guide
4. Submit PR -- fork GCX_KB, add content, open a pull request
5. Review -- GCX_Master maintainers review and merge
```

## Content Standards

### Skills

- Must have a `SKILL.md` with frontmatter (`name`, `description`)
- Must be domain-agnostic or clearly scoped
- Must include "When to Use" section

### Trifectas

- Must include all three files: `SKILL.md`, `.instructions.md`, `.prompt.md`
- Must include a `README.md` with adoption instructions
- Instructions must have `applyTo` glob in frontmatter
- Prompts must have `description` in frontmatter

### Instructions

- Must have `description` in frontmatter
- Should have `applyTo` glob for auto-loading
- Must be self-contained (no dependencies on local repo files)

### Prompts

- Must have `description` in frontmatter
- Must be self-contained
- Should include example usage

### Knowledge

- Must be factual, not opinion
- Must cite sources where applicable
- Must include a "Last Verified" date

### Patterns

- Must include context, problem, solution, consequences
- Must include at least one concrete example

## Formatting

All content follows GCX markdown standards:

- No horizontal rules (`---`) as section dividers
- Em dashes: `--` not `—`
- Mermaid: `<br/>` for line breaks, GCX Brand Pastel palette, TD for >3 boxes
- Include version history table at bottom of significant documents

## Branch Strategy

- `main` -- stable, reviewed content
- Feature branches for new contributions
- All changes via PR with at least one reviewer
