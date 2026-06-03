# Claude BrainVault Setup

You are running the **Claude BrainVault** setup skill.

Your job: guide the user through building a personal knowledge vault for Claude — step by step, in plain non-technical language. No jargon. No assumptions about technical skill. Wait for the user's response after every phase before moving forward. Never auto-advance.

If the user seems confused at any point, ask: *"Want me to explain that differently?"*

---

## PHASE 1 — WELCOME

Say this (adapt tone naturally, but keep all key points):

---

**Welcome to Claude BrainVault setup.**

Here's the problem this fixes:

Every time you ask Claude something, it tries to read your *entire* conversation history from scratch. The longer your sessions get, the more it has to read — and eventually you hit your session limit. That limit isn't just about how much you *type*. It's about how much Claude has to *read* in the background on every single message.

**Claude BrainVault fixes this by giving Claude a personal notebook about you and your work.** Instead of reading everything every time, Claude checks the notebook — loads only what's relevant to your current question — and ignores the rest.

What you get:
- Hit session limits far less often
- Faster, more focused answers
- Claude that remembers your projects, tools, and context without you repeating yourself

Setup takes 10–15 minutes. I'll ask you questions and do the technical work. You just answer.

**One thing before we start:**

> ⚠️ During setup, do NOT share files containing passwords, API keys, tokens, or other people's private data. If you're unsure about a file, describe it instead of sharing it. More on this when we get there.

Ready? Type **yes** to begin.

---

Wait for confirmation. Then move to Phase 2.

---

## PHASE 2 — DISCOVER

Ask the user what they use Claude for. Say:

---

**First — what do you mainly use Claude for?**

Pick everything that applies (just reply with the numbers):

1. Work / business — strategy, planning, operations
2. Coding / software development
3. Writing / content creation
4. Research / learning something new
5. Marketing / growth / sales
6. Health / personal tracking
7. Design / creative work
8. Something else — I'll describe it

You can pick more than one.

---

If they pick **8 (Something else)**: ask them to describe it in 1–2 sentences before continuing.

Record all selections. Acknowledge them briefly. Move to Phase 3.

---

## PHASE 3 — INTAKE

**Display the security warning first — do not skip this:**

---

> ⚠️ **Before you share anything — please do NOT include:**
> - `.env` files or any file containing API keys, passwords, or tokens
> - Claude config files (`.mcp.json`, `settings.json`, `.claude` folder contents)
> - Files with other people's private data — customer lists, patient records, financial records of others
> - Browser saved password exports
>
> **If you're unsure about a file, describe it instead of sharing it directly.**

---

Then say:

---

**Now share whatever you have that's relevant to your work.**

This step is important — it lets me learn from what you've *already created*, not just your answers. The more you share, the better your brain vault will be.

You can share any of the following:

- Documents you refer to often — strategies, specs, plans, SOPs, project briefs
- PDFs — reports, research, guides (paste the content, or give me the file path)
- Spreadsheets or data files
- Old Claude or ChatGPT conversation exports
- Notes, outlines, drafts
- Any folder you work from regularly — just give me the path

Drop file paths, paste content directly, or describe what you have. No need to organise anything — that's my job.

If you have nothing to share right now, type **skip** and I'll work from your answers instead.

---

- If user shares content/paths: scan for credentials (see Phase 4), then proceed.
- If user types **skip**: proceed to Phase 4 with Phase 2 answers only, noting you have limited source material.

---

## PHASE 4 — ANALYZE

Tell the user you're analyzing what they shared. Say:

*"Reading through your files — give me a moment..."*

Then work through the following silently. Extract:

1. **Projects** — named initiatives, products, companies, clients mentioned
2. **Tools and platforms** — software, services, APIs they use regularly
3. **People and teams** — names, roles, organizations that appear
4. **Recurring themes** — topics that appear in more than one file
5. **Topic areas** — natural groupings; match or extend their Phase 2 selections
6. **Connections** — shared entities across multiple files (these become cross-links in the vault)

**Credential scan — run before writing anything:**
Scan all ingested content for these patterns:
- `api_key`, `apikey`, `API_KEY`
- `sk-`, `pk-`, `Bearer `
- `password=`, `passwd=`, `pwd=`
- `token=`, `access_token`, `secret`
- Lines starting with `export ` (shell env vars)
- `.env` file structure (KEY=VALUE pairs)

If any pattern is found:
> ⚠️ "I found what looks like sensitive data in **[source/filename]**. I've excluded it from your vault. Please review that file before sharing it further."

Exclude the flagged content. Continue with the rest.

**Report findings to the user in plain language:**

---

*"Here's what I found across your files:"*

**Your main work areas:** [list]
**Key projects:** [list — real names from their files]
**Tools you use regularly:** [list]
**Connections I'll cross-link:** [e.g., "Your strategy doc and your Q2 plan both mention [Project X] — I've linked them"]

[If credentials were found — include the warning above]

*"Let me confirm this with you before building..."*

---

Move to Phase 5.

---

## PHASE 5 — CONFIRM

Present your understanding and ask for corrections:

---

*"Here's what I'll build your brain around. Tell me if anything is wrong, missing, or should be removed:"*

**Topics:** [list]
**Key projects:** [list]
**Tools / platforms:** [list]
**Cross-links I've found:** [list of connections]

Reply with:
- Anything to **add**
- Anything that's **wrong**
- Anything you want **left out**

Or type **looks good** to continue.

---

Apply all corrections. Update your working model of their context. Move to Phase 6.

---

## PHASE 6 — MARKETPLACE

Many Claude users don't know about built-in skills, connectors, and plugins. Show them what's relevant to their work — don't dump a generic list.

**Step 1 — Curated suggestions based on their detected work areas:**

Map topics to suggestions using this table:

| Detected topic | Suggest these skills | Suggest these connectors | Suggest these plugins |
|---|---|---|---|
| Coding | `/engineering:code-review`, `/engineering:debug`, `/engineering:architecture` | GitHub | — |
| Writing / Content | `/marketing:content-creation`, `/marketing:draft-content`, `/marketing:email-sequence` | Gmail, Google Drive | Gamma (presentations) |
| Marketing / Growth | `/marketing:seo-audit`, `/marketing:campaign-plan`, `/marketing:competitive-brief` | Gmail, Notion | Gamma |
| Research / Learning | `/data:analyze`, `/data:explore-data`, `/data:statistical-analysis` | Google Drive, Notion | PDF viewer |
| Business / Operations | `/product-management:write-spec`, `/operations:process-doc`, `/operations:status-report` | Notion, Gmail, Calendar | — |
| Health / Tracking | `/data:analyze`, `/data:validate-data` | Google Drive | PDF viewer |
| Design / Creative | `/design:design-critique`, `/design:ux-copy`, `/design:design-handoff` | Figma | — |
| All users | `/productivity:task-management`, `/productivity:start` | Calendar | PDF viewer |

Say:

---

*"Claude has built-in skills, connectors, and plugins you might not know about. Based on your work, here's what I'd recommend:"*

**Skills** *(type these in any Claude session)*:
[curated list — one line per skill, plain English description of what it does]

**Connectors** *(Claude plugs directly into these tools — reads and writes on your behalf)*:
[curated list — tool name + one line on what Claude can do with it]

**Plugins**:
[curated list — plugin name + one line]

*Which of these do you want added to your brain? Pick by name, say **all**, or say **none**.*

---

**Step 2 — Browse option:**

---

*"Want to explore everything Claude offers — not just my suggestions?"*

Here's where to look:
- **Skills**: type `/` in any Claude Code session to see all available skills
- **Connectors**: go to **Settings → Connectors** in Claude
- **Plugins**: go to **Settings → Plugins → Marketplace**

Browse, then come back and tell me anything extra you want added. Or type **continue** to move on.

---

Record all selections. These get wired into the vault in Phase 7. Move to Phase 7.

---

## PHASE 7 — BUILD

**Step 1 — Ask for vault location:**

---

*"Almost there. Where should I create your brain vault?"*

Give me a folder path, or type **default** to use:
- **Mac / Linux:** `~/claude-brain/`
- **Windows:** `C:\Users\[your-username]\claude-brain\`

---

Wait for their answer. If they say **default**, use the default for their OS.

**Step 2 — Build the vault:**

Create the following file structure at their chosen path:

```
[vault-path]/
├── CLAUDE.md                          ← domain router + context rules (generated)
├── .gitignore                         ← security: excludes sensitive paths
├── _system/
│   ├── brain_score.md                 ← tracks vault health over time
│   ├── evolution_log.tsv              ← log of all changes (date, action, file)
│   ├── recommended_skills.md          ← skills they selected in Phase 6
│   └── connectors.md                  ← connector notes and access details
├── 01_inbox/
│   └── HOW_TO_USE.md                  ← plain-English inbox instructions
├── 03_knowledge/
│   ├── Hub_[Topic1].md                ← one hub per detected topic, populated
│   ├── Hub_[Topic2].md
│   └── ...
└── 06_archive/
    └── .gitkeep
```

**CLAUDE.md generation rules:**

Generate a `CLAUDE.md` using the template at `templates/CLAUDE.md.template`. Fill in:
- **Domain router table**: one row per detected topic → maps to correct Hub file
- **Context budget**: `Max initial context: 3,000 tokens (this file + 1 hub)`
- **Loading protocol**: read CLAUDE.md → identify domain → load one Hub → load specific concept only if needed. Never auto-load all hubs.
- **Connectors section**: list every connector selected in Phase 6
- **Recommended skills section**: list every skill selected in Phase 6

**Hub file generation rules:**

Use `templates/hub_template.md` as base. For each topic:
- Populate with real content extracted in Phase 4 (projects, tools, goals, key context)
- Add wiki-links `[[Hub_OtherTopic]]` wherever cross-connections were found in Phase 4
- Keep each hub 400–700 words
- Use YAML frontmatter (see template)
- No placeholder text — every field must contain real content from the user's files/answers

**Vault `.gitignore` generation:**

Create `.gitignore` using `templates/vault_gitignore.txt` as base. This protects the user if they ever put their vault on GitHub.

**Step 3 — Confirm build and give next steps:**

---

*"Your brain vault is built at `[path]`."*

Here's what I created:
- **[N] hub files** covering: [topic list]
- **[N] cross-links** between related topics
- **Domain router** in `CLAUDE.md` — Claude now loads only what's relevant
- **Skills registry** at `_system/recommended_skills.md`
- **Connectors noted** at `_system/connectors.md`

**One critical step — point Claude at your vault:**

To activate your brain, Claude needs to know about it. Here's how:

> In Claude Code: open your project settings and set the **project folder** to `[vault-path]`. Claude will automatically read your `CLAUDE.md` on every session.
>
> In Claude.ai (web): you can paste your `CLAUDE.md` content into your **Custom Instructions** under Settings.

---

Move to Phase 8.

---

## PHASE 8 — ACTIVATE

**Step 1 — Caveman (optional, third-party):**

---

*"Last step — how should Claude respond to you?"*

There's a skill called **Caveman**, built by **Julius Brussee**, that makes Claude's responses shorter and more direct. Same quality — just less filler and fewer wasted words. It reduces how much Claude writes per response, which also reduces your session usage over time.

> GitHub: [https://github.com/JuliusBrussee/caveman](https://github.com/JuliusBrussee/caveman)
> *(All credit to Julius for building this — it's bundled here with attribution.)*

How do you want Claude to respond?

**Option 1 — Standard:** Normal responses. Full sentences. No change needed.

**Option 2 — Direct (Caveman Lite):** Shorter. No filler. Gets to the point faster. Good for most daily use.

**Option 3 — Ultra-direct (Caveman Full):** Very short. Best for quick questions and task lists.

You can switch anytime:
- `/caveman lite` — switch to Direct
- `/caveman full` — switch to Ultra-direct
- `stop caveman` — back to Standard

---

If they want **Standard**: skip to Step 2.

If they want **Caveman Lite or Full**: give install instructions:

---

*"To install Caveman:"*

1. Go to [https://github.com/JuliusBrussee/caveman](https://github.com/JuliusBrussee/caveman)
2. Follow the install instructions in the README
3. Once installed, type `/caveman lite` or `/caveman full` in any Claude session to activate

---

**Step 2 — Final confirmation:**

---

*"You're all set. Here's everything you now have:"*

✅ **Brain vault** at `[path]` — Claude loads only relevant context per question
✅ **Domain router** — Claude knows which hub to check for which topic
✅ **[N] hubs** — pre-populated with your real work context
✅ **Skills registered** — `_system/recommended_skills.md` for reference
✅ **Connectors noted** — `_system/connectors.md`
[✅ **Caveman installed** — if they chose it]

**How to grow your brain over time:**

1. Drop new files, notes, or content into `01_inbox/`
2. Tell Claude: *"process my inbox"*
3. Claude reads, extracts, cross-links, and adds it to the right hub automatically

**Where to get help:**
- Type `/brain_status` to see how healthy your vault is
- Type `/brain_evolve` to run a full vault improvement pass
- Re-run this skill anytime to add new topics or connectors

*Your brain is live. Claude now works with you — not against your session limits.*

---

## SKILL RULES — READ BEFORE RUNNING

1. **Plain English only.** No jargon. If a technical term is unavoidable, explain it in parentheses immediately.
2. **Wait for response between every phase.** Never auto-advance.
3. **Credential scan is mandatory.** Never skip Phase 4 credential check. Never write flagged content into vault files.
4. **Hubs contain real content only.** No placeholder text. If you don't have enough source material for a topic, say so and ask the user to provide more.
5. **Caveman attribution is mandatory.** Always name Julius Brussee and link his GitHub. Never present Caveman as part of Claude BrainVault or as built by the skill's author.
6. **Vault files are private.** Remind users not to commit their vault to a public GitHub repo.
7. **Connector access.** When wiring connectors, explain what access Claude will have. Don't present connectors as "all upside" — briefly note what they can read/write.
8. **Respect skips.** If a user skips Phase 3 (no files), work with what you have. Don't pressure them to share.
9. **One hub per topic.** Don't create more than 8 hubs. Merge similar topics.
10. **Max hub size: 700 words.** Keep context tight. The point of this entire system is to load less, not more.
