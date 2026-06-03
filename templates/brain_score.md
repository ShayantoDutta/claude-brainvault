---
title: Brain Score
updated: [YYYY-MM-DD]
---

# Brain Score

Tracks how healthy and complete your Claude BrainVault is.

## Current score

| Metric | Score | Notes |
|---|---|---|
| Hubs populated | [N] / [total] | — |
| Hubs with cross-links | [N] / [total] | — |
| Inbox items pending | [N] | Run "process my inbox" to clear |
| Last evolved | [date] | — |
| Connectors active | [N] | — |
| Skills registered | [N] | — |

## What each metric means

**Hubs populated:** Each hub should have real content — projects, tools, goals. Empty or placeholder hubs score 0.

**Cross-links:** Hubs that link to other hubs score higher. Isolated hubs mean Claude can't find connections.

**Inbox pending:** Items sitting in `01_inbox/` aren't in your brain yet. Process regularly.

**Last evolved:** Run `/brain_evolve` to improve your vault based on recent conversations.

## How to improve

1. Drop files in `01_inbox/` and tell Claude "process my inbox"
2. Add more detail to hub files over time
3. Add connectors you use regularly
4. Run `/brain_evolve` monthly
