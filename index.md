---
title: ProteinCV
---

<!-- Source of the public site at https://ronxbysu.github.io/proteincv-docs/ (repository ronxbysu/proteincv-docs). Copy index.md, releases/ and _config.yml there at each release. -->

# ProteinCV

ProteinCV has two sides. The **writing side** marks a CV PDF so that any AI reading it is told the Owner withholds consent to automated processing, while the document looks and prints exactly as before. The **reading side**, the Guard, tells an ingestion pipeline whether a document carries such a Notice. Since 0.2.0 there is also the **Simulation**: a Profile of what a CV evidences, a Persona that speaks as the Owner and knows nothing else, and a Fit Report that answers a job Posting one Requirement at a time. Since 0.2.1 the Persona can be installed in a person's folder as a Claude Code skill and run in the console on a subscription. Since 0.3.0 there is a **website**: an Owner signs in, reads a skills Profile of what their CV shows, runs their Persona on a job Posting, and protects the CVs they send. Since 0.3.1 nothing needs an API key: the command line and the website run on a Claude subscription, and on the website an Owner pastes a job description, presses **Test fit**, and their Persona runs as a Claude Code skill in their own folder, with every run logged. Since 0.3.2 the website runs in Docker on the Operator's own subscription, and it reads the Notice on every CV it is given.

## Releases

- [0.1.0: the Notice and the Guard](releases/0.1.0) (branch `release-0.1.0`, tag `v0.1.0`)
- [0.2.0: the Simulation](releases/0.2.0) (branch `release-0.2.0`, tag `v0.2.0`)
- [0.2.1: the Installed Persona](releases/0.2.1) (branch `release-0.2.1`, tag `v0.2.1`)
- [0.3.0: the website](releases/0.3.0) (branch `release-0.3.0`, tag `v0.3.0`)
- [0.3.1: on the subscription](releases/0.3.1) (branch `release-0.3.1`, tag `v0.3.1`)
- [0.3.2: the website in Docker](releases/0.3.2) (branch `release-0.3.2`, tag `v0.3.2`)

## Vocabulary

Every term on these pages (Owner, Notice, Protected CV, Guard, Decision, Profile, Persona, Posting, Requirement, Fit Report, Probe) is defined in the repository's `CONTEXT.md`. The design decisions behind them are in `docs/adr`.

## Requirements, every release

- Node 22 or newer; the website (0.3.0) needs 22.13 or newer.
- `corepack enable` once, so the `pnpm` scripts resolve. Without it, replace `pnpm` with `corepack pnpm` and `-r` for the root scripts, as shown on each release page.

```bash
git clone https://github.com/ronxbysu/proteincv.git
cd proteincv
corepack enable
pnpm install
pnpm build
```

Tests build their own synthetic PDFs. Never commit a real CV; `local/` is git-ignored for personal files.
