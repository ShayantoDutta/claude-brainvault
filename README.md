# Claude BrainVault

**Stop hitting Claude session limits. Build a personal knowledge vault in 15 minutes.**

---

## The problem

Every time you ask Claude something, it reads your entire conversation history from scratch. The longer your sessions get, the more it reads — and eventually you hit your session limit. That limit isn't just about how much you type. It's about how much Claude has to *read in the background* on every single message.

## The fix

Claude BrainVault gives Claude a personal notebook about you and your work. Instead of reading everything every time, Claude checks the notebook — loads only what's relevant to your current question — and ignores the rest.

**What you get:**
- Hit session limits far less often
- Faster, more focused answers
- Claude that actually knows your projects, tools, and context — without you repeating yourself every session

---

## How it works

The skill walks you through **8 guided steps**:

| Step | What happens |
|---|---|
| 1. Welcome | Explains the problem and what you're building |
| 2. Discover | You tell Claude what you use it for |
| 3. Intake | You share your existing files, docs, and exports |
| 4. Analyze | Claude reads everything, maps your projects and connections |
| 5. Confirm | Claude shows you what it found — you correct anything wrong |
| 6. Marketplace | Claude shows you built-in skills, connectors, and plugins you might be missing |
| 7. Build | Claude creates your personal vault with real, cross-linked content |
| 8. Activate | Optional: install Caveman + open your vault in Obsidian to see it as a graph |

**No coding required. Just answer the questions.**

---

## See your vault as a graph

Your vault is plain-text notes connected by links — the exact format the free [Obsidian](https://obsidian.md) app reads. Open the folder in Obsidian and switch to **Graph View** to see your brain as a picture:

- Every topic is a **dot**
- Every connection between topics is a **line**
- Related topics cluster together; lonely dots flag a gap to fill
- Drop files into `01_inbox/`, process them, and watch the map grow

The same links Claude follows to route context are the lines you see in the graph — so you're literally looking at *how Claude sees your knowledge*. Obsidian is just a viewer; Claude doesn't need it to use your vault.

**To set it up:** download Obsidian → "Open folder as vault" → select your vault folder → click the Graph View icon.

---

## Which Claude model should I use?

**For setup (running `/claude-brainvault`): use Sonnet 4.6**

Setup involves reading your files, finding connections across documents, generating populated hub content, and following complex multi-step instructions. That needs a capable model.

| Model | For setup? | Why |
|---|---|---|
| **Sonnet 4.6** | ✅ Recommended | Strong reasoning, follows complex instructions reliably, higher rate limits on Pro than Opus |
| Haiku 4.5 | ⚠️ Not recommended | Struggles with multi-file analysis and complex rule-following — hub content will be shallow |
| Opus 4.8 | ⚠️ Not recommended | Lower rate limits on Claude Pro — you could hit a limit *during* setup, which defeats the point |

**After setup: Sonnet 4.6 for complex work, Haiku 4.5 for simple Q&A**

Once your vault is built, Claude only loads ~3,000 tokens of context per session instead of your full history. At that point, Haiku handles quick lookups and simple questions just fine. Use Sonnet for anything that requires reasoning or generating content.

**How to switch models in Claude Code:** Click the model selector at the top of your session before running `/claude-brainvault`.

---

## Install

Copy and run **one command** for your platform. That's it — skill is installed and ready.

### Mac / Linux
```bash
git clone https://github.com/ShayantoDutta/claude-brainvault.git ~/.claude/skills/claude-brainvault
```

### Windows (PowerShell)
```powershell
git clone https://github.com/ShayantoDutta/claude-brainvault.git "$env:USERPROFILE\.claude\skills\claude-brainvault"
```

### Then run the skill
Open any Claude Code session and type:
```
/claude-brainvault
```
Follow the guided setup from there.

---

## Requirements

- [Claude Code](https://claude.ai/code) **or** a Claude.ai account (web / Cowork)
- Git installed ([download here](https://git-scm.com/downloads) if you don't have it)
- 10–15 minutes

---

## Security

This skill handles your personal work context. A few important rules built into every step:

- **Never share** `.env` files, API keys, passwords, or tokens during setup
- The skill **automatically scans** ingested content for credential patterns and warns you before writing anything
- A **`.gitignore` is auto-generated** for your vault — protects you if you ever put it on GitHub
- **Connector access** is explained clearly at each step — you know exactly what Claude can read or write
- Your vault files are **private by default** — treat them that way

---

## Credits

**Claude BrainVault** — built by [Shayanto Dutta](https://www.linkedin.com/in/shayantodutta/)

**Caveman** (optional output compression, bundled in Step 8) — built by [Julius Brussee](https://github.com/JuliusBrussee/caveman)
Caveman is a standalone skill by Julius. Claude BrainVault optionally installs it during setup with full attribution. All credit to Julius for that piece.

---

## License

MIT — use it, fork it, build on it.

---

## Questions or issues?

Open an issue on this repo or reach out on [LinkedIn](https://www.linkedin.com/in/shayantodutta/).
