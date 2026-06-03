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
| 8. Activate | Optional: install Caveman for shorter, direct Claude responses |

**No coding required. Just answer the questions.**

---

## Install

### What you need
- [Claude Code](https://claude.ai/code) installed
- 10–15 minutes

### Steps

**1. Clone this repo:**
```bash
git clone https://github.com/[your-username]/claude-brainvault.git
```

**2. Copy the skill to Claude's skills folder:**

Mac / Linux:
```bash
cp -r claude-brainvault ~/.claude/skills/claude-brainvault
```

Windows (PowerShell):
```powershell
Copy-Item -Recurse claude-brainvault "$env:USERPROFILE\.claude\skills\claude-brainvault"
```

**3. Run the skill in any Claude Code session:**
```
/claude-brainvault
```

**4. Follow the guided setup.**

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

**Claude BrainVault** — built by [Sayan Dutta](https://linkedin.com/in/sayantodutta)

**Caveman** (optional output compression, bundled in Step 8) — built by [Julius Brussee](https://github.com/JuliusBrussee/caveman)
Caveman is a standalone skill by Julius. Claude BrainVault optionally installs it during setup with full attribution. All credit to Julius for that piece.

---

## License

MIT — use it, fork it, build on it.

---

## Questions or issues?

Open an issue on this repo or reach out on LinkedIn.
