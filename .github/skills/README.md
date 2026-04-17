# 📚 Skills

**This is where skills live in real AI systems.** Each folder is one skill. Each `SKILL.md` is plain-English instructions. That's the whole pattern.

## Current skills

| Folder | What it does |
|--------|--------------|
| `haiku-writer/` | Writes a 5-7-5 haiku about any topic |
| `pirate-translator/` | Rewrites text in pirate-speak |
| `math-tutor/` | Walks through math problems step-by-step |
| `caveman/` | Makes responses ultra-terse. Viral on GitHub — 30K+ stars. |

## The format

Every `SKILL.md` file has two parts:

**1. Frontmatter** (the YAML block at the top with `---`)

```yaml
---
name: skill-name
description: What this skill does, and when an AI should use it.
---
```

The `description` is what the AI reads to decide whether to use this skill. **Make it specific.** Vague descriptions get ignored.

**2. Body** — plain markdown instructions. Numbered rules, examples, format guidance, what-not-to-do. Write like you're training a smart but literal intern.

## Who reads these files?

All of these tools read `.github/skills/` automatically:

- **GitHub Copilot** in VS Code (chat + agent mode)
- **GitHub Copilot CLI**
- **GitHub Copilot cloud agent**
- Your **notebook agent** (via `load_skills_from_disk()` in `build_your_first_agent.ipynb`)
- **Claude Code** also reads `.claude/skills/` — and will fall back to `.github/skills/`
- Cursor, Windsurf, Cline, Codex — anything supporting the Agent Skills spec

One folder. Many tools. That's the whole point of a standard.

## Add your own

1. Create a new folder under `.github/skills/` — e.g. `.github/skills/dad-joke-teller/`
2. Add a `SKILL.md` file with frontmatter + instructions
3. Save. That's it — Copilot will discover it automatically
4. Try asking Copilot Chat or your notebook agent something your skill should handle

See `CHEAT_SHEET.pdf` at the repo root for writing tips.
