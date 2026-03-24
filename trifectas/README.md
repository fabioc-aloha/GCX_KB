# Trifectas

> Complete Skill + Instruction + Prompt packages ready to adopt

## What is a Trifecta?

A trifecta is the fundamental unit of Copilot customization -- three files working together:

| File | Role | Location in heir repo |
| ---- | ---- | --------------------- |
| `SKILL.md` | What Copilot **knows** | `.github/skills/{name}/SKILL.md` |
| `.instructions.md` | What Copilot **enforces** | `.github/instructions/{name}.instructions.md` |
| `.prompt.md` | What Copilot **does** | `.github/prompts/{name}.prompt.md` |

## Structure

```text
trifectas/{name}/
  SKILL.md
  {name}.instructions.md
  {name}.prompt.md
  README.md              # Adoption guide
```

## Adopting a Trifecta

1. Copy `SKILL.md` to `.github/skills/{name}/SKILL.md`
2. Copy `.instructions.md` to `.github/instructions/`
3. Copy `.prompt.md` to `.github/prompts/`
4. Adapt any repo-specific references
5. Test all three files work together

## Contributing

When promoting a trifecta:

- All three files must be present and tested
- Include a README with adoption instructions
- Remove any repo-specific hardcoded paths
- Ensure instructions have `applyTo` frontmatter
