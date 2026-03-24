# GCX Knowledge Base (GCX_KB)

> Institutional knowledge shared across all GCX repos

[![Type](https://img.shields.io/badge/Type-Knowledge_Base-blue?style=for-the-badge)](#) [![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge)](#)

## Purpose

GCX_KB is the **single source of truth** for reusable knowledge, skills, trifectas, instructions, prompts, and patterns across the GCX organization. Every heir repo (GCX_Copilot, future team repos) checks this KB before creating new content, and promotes new discoveries back to it.

This solves the institutional knowledge problem: no more reinventing wheels, no more orphaned expertise, no more inconsistent implementations across teams.

## How It Works

```
Heir Repo (e.g., GCX_Copilot)          GCX_KB (Global)
+---------------------------+        +------------------------+
| Need a new skill?         |--(1)-->| Check if it exists     |
|                           |<-(2)---| Return match or "new"  |
| Created something new?    |--(3)-->| Promote to global      |
|                           |        | Available to all heirs |
+---------------------------+        +------------------------+
```

**Step 1 -- Check Global First**: Before creating any new skill, trifecta, instruction, prompt, or pattern, search GCX_KB for existing content.

**Step 2 -- Adopt or Adapt**: If found, use it directly or adapt it with local context.

**Step 3 -- Promote New Work**: If you created something new and reusable, contribute it back to GCX_KB.

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

```
Search the GCX Knowledge Base for [topic] before I create a new [skill/trifecta/instruction]
```

**Promote after creating:**

```
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

```
trifectas/{name}/
  SKILL.md              # What Copilot knows
  {name}.instructions.md # What Copilot enforces
  {name}.prompt.md       # What Copilot does
  README.md              # Trifecta overview and adoption guide
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for the contribution workflow.

**Quick rules:**
- Check global KB before creating anything new locally
- Promote reusable content back after local validation
- Include a README with every trifecta
- Follow GCX markdown formatting standards (no `---` dividers, `--` for em dashes, `<br/>` in Mermaid)

## Ownership

| Role | Owner |
| ---- | ----- |
| Repository | GCX_Master (Fabio Correa) |
| Contributions | All GCX heir repos via PR |
| Review | GCX_Master maintainers |

## Related Repos

| Repo | Role |
| ---- | ---- |
| **GCX_Master** | Source of truth, architecture owner |
| **GCX_Copilot** | Heir/template repo |
| **GCX_KB** | Global knowledge base (this repo) |
