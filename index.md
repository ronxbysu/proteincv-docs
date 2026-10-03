---
title: ProteinCV
---

# ProteinCV

ProteinCV has two sides. The **writing side** marks a CV PDF so that any AI reading it is told the Owner withholds consent to automated processing, while the document looks and prints exactly as before. The **reading side**, the Guard, tells an ingestion pipeline whether a document carries such a Notice. Since 0.2.0 there is also the **Simulation**: a Profile of what a CV evidences, a Persona that speaks as the Owner and knows nothing else, and a Fit Report that answers a job Posting one Requirement at a time. Since 0.2.1 the Persona can be installed in a person's folder as a Claude Code skill and run in the console on a subscription.

## Releases

- [0.1.0: the Notice and the Guard](releases/0.1.0) (tag `v0.1.0`)
- [0.2.0: the Simulation](releases/0.2.0) (tag `v0.2.0`)
- [0.2.1: the Installed Persona](releases/0.2.1) (tag `v0.2.1`)

## Vocabulary

Every term on these pages (Owner, Notice, Protected CV, Guard, Decision, Profile, Persona, Posting, Requirement, Fit Report, Probe) is defined in the source repository's `CONTEXT.md`, and the design decisions behind them in its `docs/adr`. The source repository is private; the release notes are public:

- https://github.com/ronxbysu/proteincv/releases/tag/v0.1.0
- https://github.com/ronxbysu/proteincv/releases/tag/v0.2.0
- https://github.com/ronxbysu/proteincv/releases/tag/v0.2.1

## Requirements, every release

- Node 22 or newer.
- `corepack enable` once, so the `pnpm` scripts resolve. Without it, replace `pnpm` with `corepack pnpm` and `-r` for the root scripts, as shown on each release page.

```bash
git clone https://github.com/ronxbysu/proteincv.git
cd proteincv
corepack enable
pnpm install
pnpm build
```

Tests build their own synthetic PDFs. Never commit a real CV; `local/` is git-ignored for personal files.
