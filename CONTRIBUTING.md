# Contributing to GCX_KB

> How institutional knowledge flows into the global Knowledge Base

## Governance

**GCX_Master is the primary curator of GCX_KB.** Authorized users with KB access can also contribute directly.

| Role | Responsibility |
| ---- | -------------- |
| **GCX_Master** | Primary curator -- creates, curates, and publishes content to GCX_KB |
| **Authorized users** | Users with KB access can contribute ideas, trifectas, and knowledge directly |
| **Heirs (without KB access)** | Consume content via Master sync. Surface new ideas to Master for promotion |
| **GCX_KB** | Stores curated, generalized, reusable content globally |

## How Content Gets Into GCX_KB

### From GCX_Master (primary path)

```
1. Create or refine content in GCX_Master
2. Validate -- content must be tested and working
3. Generalize -- remove repo-specific paths or hardcoded values
4. Publish to GCX_KB with curated structure
5. Sync relevant content to heir repos
```

### From Authorized Users (direct contribution)

```
1. User with KB access creates or identifies reusable content
2. Validate -- content must be tested and working
3. Generalize -- remove repo-specific paths or hardcoded values
4. Submit to GCX_KB (PR or direct push, depending on permissions)
5. Follow Content Standards below
```

### From Heirs Without KB Access (feedback path)

```
1. Heir team creates something useful locally
2. Heir surfaces it to GCX_Master (message, PR, or meeting)
3. GCX_Master reviews, generalizes, and curates
4. GCX_Master publishes to GCX_KB
5. All heirs benefit via sync or direct access
```

> Heirs without KB access go through GCX_Master. Authorized users can contribute directly.

## Requesting Access

GCX_KB is a private repository. To request access, email **fabioc@microsoft.com** with a business justification. Access is granted on a case-by-case basis.

Heirs can operate fully without GCX_KB access -- GCX_Master syncs all relevant content into heir repos automatically.

## Sync to Heirs

Not everyone in GCX will have access to GCX_KB. GCX_Master handles this by syncing relevant KB content into heir repos:

- Skills and trifectas that apply to the heir's domain
- Instructions and prompts the heir's team needs
- Knowledge documents relevant to the heir's work

This means heir users get KB content automatically, without needing GCX_KB access.

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

## Branch Strategy\n\n- `main` -- stable, curated content published by GCX_Master\n- Feature branches for work-in-progress content\n- All merges reviewed by GCX_Master maintainers
