# Facilitator Guide: "Build Your First AI Agent (with Skills)" (60 min)

**Audience:** High schoolers with some Python exposure
**Goal:** They leave understanding the agent loop AND the skills pattern — and having authored their own skill *in the real production format*.
**Platform:** GitHub Codespaces (browser-only) + GitHub Models (free, Microsoft-owned, no credit card)

---

## The big-picture win

The kids don't just learn a toy pattern. They learn `.github/skills/` — the **actual industry-standard file location** that GitHub Copilot, Claude Code, Cursor, Windsurf, and every other major AI tool reads automatically. What they write in this hour will be picked up by their Copilot instance in the same Codespace, by their Claude Code later at home, by whatever AI tool they touch in college. **One folder, many tools, zero translation.**

That reframing — *"you just learned the real spec"* — is the session's payoff. And it's true: GitHub shipped Agent Skills support in December 2025 with `.github/skills/` as one of the three official paths.

---

## Why Codespaces (and why this is the right call)

The whole session happens in one browser tab. No Python installs, no VS Code installs, no terminal configuration. The kid clicks one button, waits 90 seconds, and they're in a pre-configured VS Code environment with the notebook open AND the `.github/skills/` folder visible in the tree.

1. **GitHub Copilot Free is automatically active** for every kid with a GitHub account — 2,000 completions/month and 50 chat messages/month. No verification, no credit card
2. **Works on any device with a browser** — Chromebooks, iPads, school-locked laptops, whatever
3. **The repo is the artifact.** Kids fork it and keep building after class. Their skills persist

**One warning:** everyone needs a GitHub account before class starts. See `STUDENT_PREFLIGHT.md` — send it to students in advance. If you skip this, you lose 10+ minutes to account creation.

---

## 🚨 TEST THIS TONIGHT: the Copilot payoff moment

The biggest "whoa" moment in the session depends on one thing: **does GitHub Copilot Free actually pick up the `caveman` skill from `.github/skills/`?**

**Please verify this tonight before class.** 5-minute test:

1. Open the repo you push in a Codespace
2. Wait for it to fully boot
3. Open Copilot Chat (chat icon in left sidebar, or Ctrl+Alt+I)
4. Ask: *"How does a Python dictionary work?"*
5. Watch the response. Is it caveman-speak? If yes → you're golden. If no → the lesson still works, you just need to pivot the framing (see below)

**If Copilot doesn't go caveman on Free tier:**

The lesson still lands — kids can still *read* the caveman SKILL.md file, see it's plain markdown, and understand that it would work in Copilot Pro / Claude Code / their notebook agent. You pivot the framing from "watch this" to "if you had Copilot Pro, this would make it go caveman." The notebook agent will still correctly load and use the caveman skill, which proves the point regardless.

---

## Pre-session checklist (do before kids arrive)

- [ ] Create a **public** GitHub repo with the files from this kit. Update the "Open in Codespaces" URL in `README.md` to point at it
- [ ] **Test the Copilot-caveman demo** in a Codespace (above)
- [ ] Send `STUDENT_PREFLIGHT.md` to students at least 24 hours before class
- [ ] Pre-launch a Codespace yourself to verify the devcontainer builds cleanly
- [ ] Confirm classroom machines have a modern browser
- [ ] Confirm the classroom network doesn't block `github.com`, `*.github.dev`, `models.github.ai`
- [ ] Have a backup plan (Copilot Studio, see end of doc)

**Rate limit sanity check:** GPT-4o-mini on GitHub Models free tier gives each student ~150 requests/day. Each kid has their own token — not shared. Class of 20-30 is fine.

**Token source:** Have every student generate their token via **[github.com/marketplace/models/azure-openai/gpt-4o-mini/playground](https://github.com/marketplace/models/azure-openai/gpt-4o-mini/playground)** → **Use this model** → **Get developer key**. This flow (a) records acceptance of the GitHub Models terms, and (b) generates a token pre-scoped for the Models API. Plain "zero-scope" PATs from `settings/tokens` will often hit a permission error on the first call.

**Copilot limit check:** Free tier gives each kid 2,000 completions + 50 chat messages per month. If a kid chats a lot they might burn through their 50 — completions keep working.

---

## Session flow (60 min)

### 0:00–0:05 — The hook (5 min)
Open with the slide deck. Three slides: hook (chatbots→agents), the loop, what's a skill. Then do a live demo: project the notebook, run the haiku prompt, show the agent pick haiku-writer and write a poem. Then show the agent pick pirate-translator. **"Nobody told the agent which skill to pick. It read the menu, matched your question, loaded the right instructions, and followed them."**

### 0:05–0:15 — What's an agent with skills? (10 min)
Whiteboard or slides. Three ideas:

1. **Chatbot** = input → text out. Done.
2. **Agent with skills** = input → [read menu → pick skill → load instructions → follow them] → output.
3. **A skill** = a folder with a markdown file. Title, description, instructions. That's it.

The analogy that lands: the agent is a smart new hire. You've given them a binder of SOPs (skills). When a request comes in, they flip through the table of contents, find the right SOP, read it, and do the thing. They don't memorize the whole binder — they reach for what they need.

Key point: **the model doesn't load skills on its own. Your code does.** The model says "I'd like to load `haiku-writer`" and your program decides whether to honor that. That's the safety boundary.

Name progressive disclosure explicitly: "You could have 100 skills. The agent never sees all 100 at once — just the menu. It only loads the ones it needs. That's how real systems scale."

### 0:15–0:25 — Get into the Codespace (10 min)

1. Kids go to your repo URL
2. Click **Code** → **Codespaces** → **Create codespace on main**
3. Wait ~90 seconds
4. When VS Code loads, open `build_your_first_agent.ipynb`
5. First-time kernel setup: install kernel extensions, pick Python 3.11
6. Run cells top-to-bottom
7. Paste PAT when prompted

**Common failures:**
- **"kid doesn't have a GitHub account yet"** — pair them with a buddy
- **"permission denied" on the first API call** — their token wasn't generated from the Models playground. Send them to **[github.com/marketplace/models/azure-openai/gpt-4o-mini/playground](https://github.com/marketplace/models/azure-openai/gpt-4o-mini/playground)** → **Use this model** → **Get developer key** → generate. That flow auto-scopes the token for GitHub Models and also records the terms acceptance.
- **"I made a token at github.com/settings/tokens with zero scopes and it still fails"** — same fix as above; use the playground route.

See `STUDENT_PREFLIGHT.md` for the full list.

### 0:25–0:30 — Show them the file tree (5 min)
This is where you slow down and make the migration real.

*"Before we go further, look at the file tree on the left side of VS Code. See the `.github/skills/` folder? Expand it. Each folder is a skill. Click one. Open the SKILL.md file. **Read it.** That's what a real skill looks like — plain markdown, plain English, no code."*

Let them read for 30 seconds. Then:

*"In a lot of AI classes, you'd write skills as Python strings inside a dictionary. That's training wheels. This class, we're doing it the real way. GitHub published this exact folder structure — `.github/skills/*/SKILL.md` — as an open standard. Claude Code reads it. GitHub Copilot reads it. Cursor reads it. Your notebook agent is about to read it too. One folder, many tools."*

### 0:30–0:40 — Run the agent (10 min)
Kids run through Steps 4, 5, 6, 7 of the notebook. They see the `load_skills_from_disk()` function parse each `SKILL.md` file, see the four skills register, see the agent loop pick a skill and load it.

Encourage them to change the prompt a few times. Try prompts that match, prompts that don't, prompts that could match two skills.

### 0:40–0:45 — **The Copilot reveal** (5 min)
This is the single biggest "whoa" moment. Everyone stops and does this together.

*"OK, now for the payoff. Open Copilot Chat — click the chat icon on the left sidebar. Ask it anything normal, like 'how does a for loop work?'"*

If Copilot goes caveman → watch them realize what just happened. **"The exact same file your notebook agent just used is also being read by Copilot. Same file. Same format. Two different tools. That's the whole point of a standard."**

If Copilot doesn't go caveman (Free tier might not honor skills) → *"Copilot Free has limited skill support, but Copilot Pro and Claude Code both read this exact file. Your skill is portable across every major AI tool — you just can't see it for free in this particular chat."* and show a screenshot if you have one ready.

### 0:45–0:55 — Write your own skill (10 min)
Direct them to the cheat sheet — yellow fill-in-by-hand template. *"Plan your description and instructions on paper first."*

Then in VS Code:
1. Right-click `.github/skills/` → New Folder → name their skill (e.g. `dad-joke-teller`)
2. Right-click new folder → New File → `SKILL.md`
3. Copy the template from the notebook, edit it
4. Save
5. Re-run the `load_skills_from_disk()` cell
6. Ask the agent something that should trigger their skill

**Common stuck points:**
- **Vague descriptions** → agent ignores it. Fix: be specific about WHEN to use it
- **Instructions too short** → agent hallucinates. Fix: pretend you're training an intern
- **Frontmatter formatting wrong** → skill doesn't load. Most common: missing `---` markers, or `name:` has uppercase letters. YAML is picky

**Copilot as an assist:** kids stuck writing their skill can ask Copilot Chat for help. *"Write instructions for a skill that generates funny excuses for missing homework."* Copilot drafts. They edit. Three AI systems just cooperated — Copilot wrote the file, the notebook agent loaded it, the model followed it.

### 0:55–0:58 — Show and tell (3 min)
Pick 2-3 volunteers. Ask:
- What skill did you build?
- Did it get picked by the agent?
- If not — was it the description, the instructions, or the prompt?

That third question is gold — it opens the door to prompt engineering without you having to lecture.

### 0:58–1:00 — The "what now" (2 min)
Leave them with this:

**"Everything you used today is free forever at this tier. Your Codespace stays in your GitHub account. Your Copilot keeps working. Your PAT keeps working. And the skill you just wrote? It's in the real production format. Fork this repo, push it, and anyone in the world can clone it and use your skill in Copilot, Claude Code, Cursor, or their own agent. You just shipped your first piece of the AI ecosystem."**

---

## Talking points if a kid asks...

**"Wait, is `.github/skills/` real?"**
Yes. GitHub shipped it in December 2025 as part of the Agent Skills open spec. Copilot, Copilot CLI, and the Copilot cloud agent all read it. Claude Code reads `.claude/skills/` (same format, different folder). Copilot reads both.

**"Why not just put all the instructions in the system prompt?"**
You could, for 3 skills. Try it with 300. The context window fills up, the model gets confused, and every request costs more because you're sending everything every time. Progressive disclosure fixes all three problems.

**"How is this different from just prompting?"**
The agent is making a *decision* — which skill to load — based on the user's question. That's the agent part.

**"Can the agent invent new skills?"**
Not in this version. Some production systems let agents write and save new skills. Safety cans of worms.

**"How is this different from GitHub Copilot?"**
Copilot is an AI that helps *you* write code. Your agent is an AI that *is* code — it decides things and takes actions. Copilot is an *assistant*; what you built is an *agent*. But both now read the same `.github/skills/` files, which is wild when you think about it.

**"Why did my skill not get picked?"**
Almost always the description. Make it more specific. Say *when* to use the skill, not just *what it does*.

**"Can I keep using this after class?"**
Yes. Everything free. Fork the repo, keep building.

---

## Extensions (follow-up session)

- **Scripts in skills:** the real spec supports scripts and resources inside the skill folder. Add a `convert.py` that a skill references
- **Personal skills:** `~/.copilot/skills/` for skills that span across all your repos
- **Publish to Awesome Copilot:** the community repo at github/awesome-copilot accepts skill contributions
- **MCP servers:** the next layer up — dynamic tools that skills can reference

---

## Backup plan: Copilot Studio path

If GitHub services have an outage:

1. Kids go to `copilotstudio.microsoft.com`
2. Create a new agent with instructions
3. Add topics (= skills, roughly)
4. Test in the chat panel

Less "I wrote a file on disk," more "I configured in a UI." Keep the notebook as homework.

---

## After the session

- Their Codespace persists
- Their Copilot stays active
- Their skill is in the real format
- Invite them to fork and share what they build
