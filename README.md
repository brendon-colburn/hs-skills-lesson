# 🤖 Build Your First AI Agent

**A 60-minute workshop for high school students.** You'll build a real AI agent that reads skills from disk and picks the right one for any question. The skills you write here work in GitHub Copilot, Claude Code, Cursor, and every other major AI tool — because `.github/skills/` is an open standard.

---

## 🚀 Start here (click this)

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/YOUR_USERNAME/YOUR_REPO_NAME?quickstart=1)

> Replace `YOUR_USERNAME/YOUR_REPO_NAME` in the link above after you create the repo.

**What happens when you click it:**
1. GitHub spins up a free cloud computer just for you (~90 seconds)
2. VS Code opens in your browser with everything pre-installed
3. The notebook file `build_your_first_agent.ipynb` is ready to go
4. You start building

**No installs. No terminal setup. Everything just works.**

---

## 👉 What you're building

By the end of the hour, you'll have:

- A real AI agent that reads a **menu of skills from disk** and picks the right one for any question
- Your own custom skill — written in plain English, saved as a `SKILL.md` file in `.github/skills/`
- An understanding that the file you wrote is the **same format** used by Copilot, Claude Code, and every major AI tool

Here's what it looks like when it runs:

```
👤 USER: Write me a haiku about pizza.
  📖 Agent loaded skill: haiku-writer
🤖 AGENT: Melted cheese stretches /
          Pepperoni sun rising /
          Friday night feast glows
          (5 / 7 / 5 ✓)
```

The agent **decided on its own** to load the `haiku-writer` skill — by reading `.github/skills/haiku-writer/SKILL.md`.

---

## 📋 Before class — 5-minute pre-flight

**Read [STUDENT_PREFLIGHT.md](STUDENT_PREFLIGHT.md).** You need two things before class starts:

1. A free GitHub account
2. A GitHub Models token — generated from the [GPT-4o mini playground](https://github.com/marketplace/models/azure-openai/gpt-4o-mini/playground) by clicking **Use this model** → **Get developer key**

Takes 5 minutes. Do it before class so we can hit the ground running.

---

## 📁 What's in this repo

| Path | What it is |
|------|------------|
| `.github/skills/` | **Where skills live.** Open this folder to see the real format. |
| `.github/skills/caveman/` | A real-world viral skill ([30K+ stars on GitHub](https://github.com/JuliusBrussee/caveman)) that shows how skills are portable. |
| `.github/skills/haiku-writer/` | Starter skill: writes 5-7-5 poems |
| `.github/skills/pirate-translator/` | Starter skill: rewrites text as a pirate |
| `.github/skills/math-tutor/` | Starter skill: walks through math problems |
| `build_your_first_agent.ipynb` | **The notebook you'll work in.** Run cells top-to-bottom. |
| `CHEAT_SHEET.pdf` | One-page reference — keep it open in a tab. |
| `STUDENT_PREFLIGHT.md` | The 5-minute setup to do before class. |
| `FACILITATOR_GUIDE.md` | For the instructor. |
| `.devcontainer/` | Configuration that makes the Codespace work. |

---

## 🧠 Why `.github/skills/`?

This is the file location GitHub published as an open standard in December 2025. All of these tools read it automatically:

- **GitHub Copilot** (chat + agent mode in VS Code)
- **GitHub Copilot CLI**
- **GitHub Copilot cloud agent**
- **Claude Code** (also reads `.claude/skills/` — same format)
- **Cursor, Windsurf, Cline, Codex** — all support the Agent Skills spec

**One folder. Many tools. Zero translation.** The skill you write here tomorrow works everywhere, forever.

---

## 🛟 Something broken?

Check the **back of the cheat sheet** — fixes for the 7 most common problems.

Still stuck? Raise your hand.

---

## 🎁 What you get to keep

Everything in this repo is yours. After class:

- **The Codespace** stays in your GitHub account (60 hours/month free)
- **Your notebook** with whatever skills you built — they persist
- **GitHub Copilot Free** (2,000 completions + 50 chat messages/month) keeps working forever
- **Your PAT** keeps working for GitHub Models (~150 free requests/day)
- **Your skills** in `.github/skills/` — fork and share them

---

*Built with GitHub Models. Free. No credit card. Runs in your browser.*
