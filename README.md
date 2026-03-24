# GCX Knowledge Base (GCX_KB)

> Institutional knowledge shared across all GCX repos

[![Type](https://img.shields.io/badge/Type-Knowledge_Base-blue?style=for-the-badge)](https://github.com/fabioc-aloha/GCX_KB) [![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge)](https://github.com/fabioc-aloha/GCX_KB)

## Purpose

GCX_KB is the **single source of truth** for reusable knowledge, skills, trifectas, instructions, prompts, and patterns across the GCX organization. **GCX_Master curates and publishes content here** for the benefit of all heir repos (GCX_Copilot, future team repos).

This solves the institutional knowledge problem: no more reinventing wheels, no more orphaned expertise, no more inconsistent implementations across teams.

## Governance Model

```text
GCX_Master (Curator)              GCX_KB (Global Store)           Heirs (Consumers)
+--------------------+          +---------------------+         +------------------+
| Creates & curates  |--(push)->| Stores globally     |         | GCX_Copilot      |
| skills, trifectas, |          | Available to all    |<-(read)-| Team repos       |
| knowledge, etc.    |          | with access         |         | Vendor repos     |
+--------------------+          +---------------------+         +------------------+
                                   ^          |                         |
                              Authorized  Direct access          Synced by Master
                              users can   (if authorized)      (for those without)
                              contribute
```

**Who writes to GCX_KB:**

- **GCX_Master** -- Primary curator. Creates, curates, and publishes content
- **Authorized users** -- Users with KB access can also contribute directly by promoting ideas, trifectas, and knowledge

**Who reads from GCX_KB:**

- **Direct access** -- Authorized users can clone GCX_KB and browse directly
- **Synced via Master** -- GCX_Master syncs relevant KB content into heir repos so users without KB access still benefit

**Heirs without KB access** surface reusable content to GCX_Master for curation and promotion.

## Requesting Access

GCX_KB is a private repository. To request access:

1. Email **<fabioc@microsoft.com>**
2. Include a **business justification** explaining why you need direct KB access
3. Access is granted on a case-by-case basis

**Heirs can operate fully without GCX_KB access.** GCX_Master syncs all relevant content (skills, trifectas, instructions, prompts) into heir repos. Direct KB access is convenient but not required.

## Repository Structure

| Folder | Contents | Description |
| ------ | -------- | ----------- |
| `knowledge/` | Domain knowledge docs | CX concepts, platform guides, reference material |
| `skills/` | Copilot skill files | Reusable SKILL.md files for any GCX repo |
| `trifectas/` | Skill + Instruction + Prompt sets | Complete trifecta packages ready to adopt |
| `instructions/` | Auto-loaded rule files | Reusable instruction files (.instructions.md) |
| `prompts/` | Workflow templates | Reusable prompt files (.prompt.md) |
| `patterns/` | Architecture patterns | Proven patterns, templates, and reference implementations |

## Usage

### From Any Heir Repo

**Search before creating:**

```text
Search the GCX Knowledge Base for [topic] before I create a new [skill/trifecta/instruction]
```

**Promote after creating:**

```text
Promote [file/skill/trifecta] to the GCX Knowledge Base
```

### Naming Conventions

| Type | Pattern | Example |
| ---- | ------- | ------- |
| Knowledge | `knowledge/{domain}.md` | `knowledge/cpm-integration.md` |
| Skill | `skills/{name}/SKILL.md` | `skills/markdown-mermaid/SKILL.md` |
| Trifecta | `trifectas/{name}/` | `trifectas/cpm-integration/` |
| Instruction | `instructions/{name}.instructions.md` | `instructions/security.instructions.md` |
| Prompt | `prompts/{name}.prompt.md` | `prompts/survey-design.prompt.md` |
| Pattern | `patterns/{name}.md` | `patterns/csar-loop.md` |

### Trifecta Structure

Each trifecta folder contains a complete skill + instruction + prompt set:

```text
trifectas/{name}/
  SKILL.md              # What Copilot knows
  {name}.instructions.md # What Copilot enforces
  {name}.prompt.md       # What Copilot does
  README.md              # Trifecta overview and adoption guide
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

**Key rules:**

- GCX_Master is the primary curator of GCX_KB
- Authorized users with KB access can also contribute directly
- Heirs without KB access surface reusable content to Master for promotion
- All content is reviewed and generalized before publication
- Follow GCX markdown formatting standards (no `---` dividers, `--` for em dashes, `<br/>` in Mermaid)

## Ownership

| Role | Owner |
| ---- | ----- |
| Curator / Publisher | GCX_Master (Fabio Correa) |
| Contributors (direct) | Authorized users with KB access |
| Consumers (direct) | Authorized GCX team members |
| Access requests | <fabioc@microsoft.com> (with business justification) |
| Consumers (synced) | All heir repos via Master sync |
| Review | GCX_Master maintainers |

## Related Repos

| Repo | Role |
| ---- | ---- |
| **GCX_Master** | Source of truth, architecture owner |
| **GCX_Copilot** | Heir/template repo |
| **GCX_KB** | Global knowledge base (this repo) |
