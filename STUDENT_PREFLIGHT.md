# 🛫 Before Class: 5-Minute Pre-Flight

**Do this before class starts so we can jump straight to building.** Reading time: 2 minutes. Setup time: 3 minutes.

---

## What you need

1. A GitHub account (free)
2. A **GitHub Models token** (your password for talking to AI models — generated for you by the Models playground)

That's it. No credit card. Just a browser.

> 🚨 **Use a personal email (Gmail, Outlook, iCloud, etc.) — NOT your school `.edu` email.**
> GitHub blocks most `.edu` domains at signup, and if you get stuck on this in class you can't move forward. If you only have a school email, **make a free personal one before class** (gmail.com takes 2 minutes). You can always link your `.edu` later via GitHub Student Developer Pack.

---

## Step 1 — Make a GitHub account (skip if you already have one)

Go to **[github.com/signup](https://github.com/signup)** and follow the prompts.

Tips:
- Use an email you actually check — you'll need to verify it
- Your username will be visible to anyone who sees your code, so pick something you won't regret
- The free plan is all you need

---

## Step 2 — Get your GitHub Models token

This is the password your notebook uses to make AI models respond. The easiest way to get one is straight from the Models playground — it generates a token that's already scoped correctly for what we need.

1. Sign in to GitHub and open **[github.com/marketplace/models/azure-openai/gpt-4o-mini/playground](https://github.com/marketplace/models/azure-openai/gpt-4o-mini/playground)**
2. If it's your first time, accept the GitHub Models terms
3. Click the **Use this model** button (top right of the playground)
4. A dialog opens with setup instructions — click **Get developer key** (or "Create personal access token")
5. GitHub takes you to a pre-filled token form. **Don't change anything.** Just scroll down and click **Generate token**
6. **COPY THE TOKEN NOW.** It starts with `github_pat_` or `ghp_` followed by random letters and numbers.

> ⚠️ You will **never see the token again** after you leave this page. Copy it somewhere safe like a notes app. If you lose it, just repeat the steps above — no big deal.

> 💡 **Why this way?** Going through the playground auto-configures the token with exactly the right permissions for GitHub Models. Making a plain token at `github.com/settings/tokens` often trips a "permission denied" error on the first API call.

---

## Step 3 — Paste it somewhere temporary

Put the token in a notes app, a text file, anywhere you can paste from later. You'll need it the moment class starts.

**Do not:**
- Paste it into any shared chat
- Commit it to any repo
- Share it with anyone, not even a friend

If you think someone else saw it, go to [github.com/settings/tokens](https://github.com/settings/tokens) and click "Delete" next to it. Then repeat Step 2 to make a new one.

---

## Step 4 — (Optional) Test the Codespace boot

This is totally optional, but if you want to make class smoother:

1. Go to the repo link your instructor shared
2. Click the green **Code** button → **Codespaces** tab → **Create codespace on main**
3. Wait ~90 seconds while it boots
4. When VS Code loads in your browser, you can close the tab — you just pre-warmed the environment

This trims 90 seconds off class time for you. Not required.

---

## ✅ You're ready when you have:

- [ ] A GitHub account you can sign in to (with a **personal** email, not `.edu`)
- [ ] A GitHub Models token (`github_pat_...` or `ghp_...`) copied somewhere you can paste from
- [ ] Accepted the GitHub Models terms at least once (happens automatically the first time you open the playground)
- [ ] A browser (Chrome, Edge, Safari, or Firefox — all fine)

---

## 🚨 Day-of-class heads up: the token popup

When class starts and you run the cell that asks for your token, **a text input box pops up at the very TOP of the VS Code window** — not inside the notebook cell. Paste your token into that top box and press **Enter**.

This trips up almost everyone. Just remember: **look up**, paste, press Enter.

See you in class. 🤖
