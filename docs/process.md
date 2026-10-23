# How we work

## Roles

| Role | Who | Owns |
|---|---|---|
| **Product owner** | martemagua | *What* gets built and *why*, the order, and whether a piece of work is accepted |
| **Development team + tech lead** | Claude | *How* it gets built: options with effort and risk, the code, demos, explanations |

Two ground rules:

- Claude doesn't build a story until it is **ready** (see below).
- The product owner doesn't accept a story until it is **done** (see below).

## The steps

1. **Vision** — who it's for, why it exists, what success looks like → [vision.md](vision.md)
2. **How it works** — enough technical background to judge what's possible → [glossary.md](glossary.md)
3. **Feature inventory** — everything on the table, grouped into *epics*
4. **Prioritise** — must / should / could / won't, then cut to the first release (the *MVP*)
5. **User stories** — each feature written from the visitor's side, with acceptance criteria
6. **Spikes** — short technical experiments for anything uncertain; they answer a question, they don't ship
7. **Release plan** — v0.1, v0.2… each one live and playable
8. **Build, demo, learn** — repeat

## The board

GitHub Project **martemagua**, one card per issue:

| Column | Meaning |
|---|---|
| **Backlog** | Ideas and stories not yet ready to build |
| **Ready** | Meets the Definition of Ready; can be picked up |
| **In progress** | Being built on a branch |
| **Review** | A pull request is open and waiting for the product owner |
| **Done** | Meets the Definition of Done and is merged |

## Definition of Ready

A story can move to **Ready** when:

- [ ] It is written as *"As a …, I want … so that …"*
- [ ] It has acceptance criteria someone could check without reading code
- [ ] It is small enough to finish in one pull request
- [ ] Open technical questions are answered (by a spike if needed)

## Definition of Done

A story can move to **Done** when:

- [ ] Every acceptance criterion passes, checked on a phone **and** a desktop
- [ ] The pull request explains what changed, why, and how it works in plain language
- [ ] Any technical choice made along the way has a [decision record](decisions/)
- [ ] New technical terms are added to the [glossary](glossary.md)
- [ ] The product owner approved and merged it

## How a change reaches the site

```
issue (story)  →  branch  →  commits  →  pull request  →  review  →  squash merge to main  →  deploy
```

Nothing reaches `main` — and so nothing reaches martemagua.com — without the
product owner merging it. GitHub enforces this (see *Repository settings*).

## Repository settings

What is configured on GitHub, and why. If a setting changes, update this list.

| Where | Setting | Why |
|---|---|---|
| General → Pull Requests | Squash merging only; message = PR title and description | One story = one commit on `main`; the history reads like a changelog |
| General → Pull Requests | Automatically delete head branches; always suggest updating PR branches | Fewer leftover branches, fewer stale PRs |
| General → Features | Wiki off | Docs live in the repo, next to the code |
| Rules → Ruleset on `main` | Require a pull request (0 approvals); block force pushes; restrict deletions; require linear history | Nothing reaches `main` without a PR the product owner merges. 0 approvals because GitHub doesn't let you approve a PR under your own account — the merge click is the approval |
| Code security | Secret scanning + push protection; Dependabot alerts + security updates | Blocks pushes containing keys; warns about vulnerable libraries |
| Project board | Auto-add issues and PRs; closed / merged → Done; fields Size, Priority, Release | The board updates itself; prioritising happens in the fields |

Later: *require status checks to pass* once the project has automated checks.

## Keeping a public repo safe

This repository is public. That is fine because nothing sensitive ever goes in it:

- **Never commit:** passwords, API keys, tokens, `.env` files, private
  hostnames or IP addresses of the home server, or visitors' data.
- Secrets live on the server only, and the code reads them from the environment.
- `.gitignore` blocks the usual secret files by default.
- Turn on GitHub's free safety nets under **Settings → Code security**: *secret
  scanning* with *push protection* (blocks a push that contains a key), and
  *Dependabot alerts* (warns about vulnerable libraries).
