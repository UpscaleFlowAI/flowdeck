# Demo Walkthrough — Claude Routines with GitHub Push Trigger

Use this as your on-camera guide. Each section tells you what to show, what to say, and what to type.

---

## Beat 1 — Intro (on camera / screen share: browser)

**Show:** Your face or the FlowDeck landing page in a browser.

**Say (rough talking points):**
- "In this video I'm going to show you how Claude can automatically generate marketing content every time you push a new feature to GitHub."
- "We're using a fictional product called FlowDeck — a monitoring dashboard for automation agencies."
- "The magic here is Claude Routines. You set up a routine with a GitHub trigger, and every push to main kicks off an AI task — in our case, writing social media posts, an email, and release notes, all in Lebanese Arabic."

---

## Beat 2 — Show the repo on GitHub (screen share: github.com)

**Show:** The repo page on GitHub. Scroll through the files briefly — README, CHANGELOG, FEATURES, the feature specs in `src/features/`, the marketing brief in `docs/`.

**Say:**
- "Here's the repo. It's a simple static site — HTML, Markdown, no build step."
- "The important files for the routine are the feature specs in `src/features/` and the marketing brief in `docs/`. The routine reads these to understand what to write and how to write it."

---

## Beat 3 — Show the Claude routine setup (screen share: claude.ai → Routines)

**Show:** Claude.ai → Routines panel → click into the routine you created.

**Say:**
- "Here's the routine I set up. The prompt tells Claude to read the latest commit, check for new features, and generate marketing copy in Lebanese Arabic."
- "The trigger is a GitHub push event on the main branch of this repo. Every time I push, Claude runs this automatically."
- Point out: the model (Sonnet), the trigger type (GitHub push), the target branch (main).

---

## Beat 4 — Add the new feature (screen share: VS Code + terminal)

**Show:** VS Code with the repo open. Open the terminal.

**Say:**
- "Now I'm going to add a new feature — an AI Workflow Summarizer that lets users ask natural-language questions about their automation history."
- "I've pre-staged the files so this is quick."

**Run these commands (type them, don't paste — looks better on camera):**

```bash
# Copy the feature spec into the features directory
cp STAGED_FEATURE/ai-summarizer.md src/features/ai-summarizer.md
```

**Show** the file briefly in VS Code — scroll through it so viewers see it's a real spec.

```bash
# Insert the changelog entry at the top of CHANGELOG.md
sed -i '7r STAGED_FEATURE/changelog-entry.md' CHANGELOG.md
```

**Optionally show** the updated CHANGELOG in VS Code.

```bash
# Stage, commit, and push
git add .
git commit -m "feat: add AI workflow summarizer"
git push
```

**Say:**
- "That's it — new feature spec, updated changelog, pushed to main."

---

## Beat 5 — Watch the routine fire (screen share: claude.ai → Routines)

**Show:** Switch to Claude. Open the Routines panel. The routine should trigger within seconds.

**Say:**
- "And there it is — the routine picked up the push and it's running."
- Wait for it to finish.
- "Let's look at the output."

**Show:** Scroll through the generated marketing copy. Point out:
- The X/Twitter post in Lebanese Arabic
- The LinkedIn post
- The email with subject line
- The Instagram caption with emojis
- The YouTube thumbnail options
- The English release notes blurb at the bottom

**Say:**
- "Everything is in Lebanese Arabic, exactly the dialect and tone we specified in the marketing brief."
- "The product names are all transliterated — فلو ديك instead of FlowDeck, إن ايت إن instead of n8n."
- "And notice the release notes at the bottom are in English, because that's what goes on the GitHub release."

---

## Beat 6 — Wrap up (on camera)

**Say:**
- "So that's Claude Routines with a GitHub trigger."
- "Every push to main automatically generates localized marketing copy — no manual prompting, no copy-pasting."
- "You could adapt this to generate documentation, create Jira tickets, post Slack updates, translate release notes — basically any downstream task that should happen when code ships."
- CTA: "If you want to see more Claude automations, subscribe and I'll see you in the next one."

---

## Troubleshooting

If the routine doesn't fire after the push:

1. **Check the trigger config:** In Claude → Routines → your routine → Trigger, make sure it's set to "GitHub push" on the correct repo and branch (`main`).
2. **Check connector permissions:** Go to Claude → Settings → Connectors → GitHub. Verify the GitHub connector is authorized and has access to this specific repository.
3. **Check the push landed on main:** Run `git log --oneline -1 origin/main` to confirm your commit is the latest on remote main.
4. **Wait 10–15 seconds:** There can be a brief delay between the GitHub webhook firing and the routine starting.
5. **Check the routine run history:** In the Routines panel, look for a failed or queued run — the error message will usually point to the issue.
