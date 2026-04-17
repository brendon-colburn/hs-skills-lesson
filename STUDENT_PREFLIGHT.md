# 🛫 Before Class: 5-Minute Pre-Flight

**Do this before class starts so we can jump straight to building.** Reading time: 2 minutes. Setup time: 3 minutes.

---

## What you need

1. A GitHub account (free)
2. A Personal Access Token, aka PAT (your password for talking to AI models)

That's it. No credit card. No school email required. Just a browser.

---

## Step 1 — Make a GitHub account (skip if you already have one)

Go to **[github.com/signup](https://github.com/signup)** and follow the prompts.

Tips:
- Use an email you actually check — you'll need to verify it
- Your username will be visible to anyone who sees your code, so pick something you won't regret
- The free plan is all you need

---

## Step 2 — Create a Personal Access Token (PAT)

This is the password your notebook uses to make AI models respond. It's important that you do this right — the token needs to have **zero scopes** (zero special permissions).

1. Sign in to GitHub and go to **[github.com/settings/tokens](https://github.com/settings/tokens)**
2. Click **Generate new token** → **Generate new token (classic)**
3. Fill in the form:
   - **Note:** `ai-class` (or whatever you want — it's just a label)
   - **Expiration:** 7 days (for safety — tokens shouldn't live forever)
   - **Scopes:** leave **everything unchecked** ✅
4. Scroll to the bottom and click **Generate token**
5. **COPY THE TOKEN NOW.** It starts with `ghp_` followed by random letters and numbers.

> ⚠️ You will **never see the token again** after you leave this page. Copy it somewhere safe like a notes app. If you lose it, just generate a new one — no big deal.

---

## Step 3 — Paste it somewhere temporary

Put the token in a notes app, a text file, anywhere you can paste from later. You'll need it the moment class starts.

**Do not:**
- Paste it into any shared chat
- Commit it to any repo
- Share it with anyone, not even a friend

If you think someone else saw it, go back to [github.com/settings/tokens](https://github.com/settings/tokens) and click "Delete" next to it. Generate a new one.

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

- [ ] A GitHub account you can sign in to
- [ ] A `ghp_...` token copied somewhere you can paste from
- [ ] A browser (Chrome, Edge, Safari, or Firefox — all fine)

See you in class. 🤖
