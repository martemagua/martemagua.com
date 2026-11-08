# CLAUDE.md

Read this first in every session. It says what this project is, who you are
working with, and the rules we agreed. Keep it current: when a rule changes,
change it here in the same pull request.

## What this is

**martemagua.com** — an interactive sea on a web page. Visitors touch it, tilt
their phone and type words (*o mar tem ___*); every word they write becomes
something the sea has, and things in the sea interact with each other.
The nickname: **mar + tem + água**, "the sea has water".

Full vision, principles and non-goals: [docs/vision.md](docs/vision.md).

## Who you work with

The repo owner is the **product owner** and is *not* a developer. This is a
learning project: the goal is a site they enjoy **and** can explain end to end.

- Explain in plain language. Name the trade-off, not just the answer.
- Bring decisions to them as options with effort and risk; give a
  recommendation, but they decide *what* and *why*.
- Never assume knowledge of a term — if a new one appears, add it to
  [docs/glossary.md](docs/glossary.md).

## How we work

Full process: [docs/process.md](docs/process.md). The rules that matter every time:

- **Only build stories that are Ready** (Definition of Ready in process.md). If a
  request isn't, help write the story and acceptance criteria first.
- **Every change goes through a pull request** from its own branch. `main` is
  protected; never push to it directly. PRs are **squash-merged**, so the PR
  title becomes the commit message on `main` — write it as a clear summary.
- **Fill in the PR template** (`.github/pull_request_template.md`): what
  changed, why, how it works in plain language, how to check it on a phone and
  a desktop, decisions and new terms.
- **Record real technical decisions** in `docs/decisions/` using the template.
  Never edit an accepted record; supersede it with a new one.
- **Keep pull requests small** — one story each.
- The product owner merges. Never merge, approve, or close their work on their behalf.

## Product rules

These come from the vision's principles; check new work against them.

- **Phone first.** Touch and tilt are the main controls; mouse and keyboard
  must still work. Check every change at phone width.
- **Alive at rest.** The page moves before anyone touches it.
- **Every word gets a response**, including unknown ones.
- **Innocent and private.** No accounts, no tracking, no analytics that
  identify people, no personal data. Visitor progress lives only in the
  browser's local storage.
- **Easy to explain beats clever.** Prefer the simple, readable solution; if
  something clever is truly needed, explain it in the PR and a decision record.
- **Brazilian Portuguese** for all visitor-facing text. Accept European
  Portuguese spellings and unaccented typing as input. English and German come later.
- **Accessibility:** respect `prefers-reduced-motion`; visible keyboard focus;
  sound only after the visitor turns it on.

## Security (this repo is public)

Never commit passwords, API keys, tokens, `.env` files, private hostnames or IP
addresses of the home server, or visitor data. Secrets live on the server and
are read from the environment. GitHub secret scanning with push protection is on.

## Where things are

| Path | Holds |
|---|---|
| `docs/vision.md` | Vision, principles, non-goals, success |
| `docs/process.md` | Roles, board, Definition of Ready / Done, repo settings |
| `docs/decisions/` | Decision records (`0000-template.md` to start one) |
| `docs/glossary.md` | Plain-language terms |
| `prototype/` | Throwaway prototype — reference only, **not** the product |
| `.github/` | PR template, issue templates (user story, spike) |

## Current state

**Planning phase — no product code yet.** We are at step 3 of the process
(feature inventory). The tech stack is not chosen; it will be decided in
decision records before the first story is built. Do not reuse code from
`prototype/` without reviewing it like new code.

To try the prototype: open `prototype/sea.html` in a browser (no build step).
