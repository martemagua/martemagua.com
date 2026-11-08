# Glossary

Every technical term we use, in plain words. New terms are added in the pull
request that first uses them.

## How a website works

| Term | Meaning |
|---|---|
| **Domain** | The name people type: `martemagua.com`. |
| **DNS** | The internet's phone book. It turns the domain into the address of my server. |
| **Server** | The computer that hands out the website's files (mine, at home). |
| **Web server** | The program on the server that answers requests and sends files — e.g. *Caddy* or *nginx*. |
| **Reverse proxy** | A web server that sits in front of several apps and sends each request to the right one, based on the domain or path. |
| **HTTPS / TLS** | Encryption between the visitor and the server — the padlock in the browser. Needs a *certificate*. |
| **Browser** | The app on the visitor's device (Safari, Chrome…) that downloads the files and runs them. |
| **HTML** | The structure of the page: headings, text, buttons. |
| **CSS** | The look: colours, fonts, layout, animations. |
| **JavaScript (JS)** | The behaviour: everything that reacts or moves. |
| **Canvas** | A drawing surface in the page. JavaScript paints the sea on it. |
| **Frame / 60 fps** | One redraw of the canvas. Smooth animation means about 60 redraws per second. |
| **Static site** | A website that is only files. The server just hands them out; all logic runs in the browser. |
| **Backend** | Code that runs on the server. Needed for anything shared between visitors, like a word log. |
| **API** | A defined way for one program to talk to another — e.g. the page sending a word to the backend. |
| **Local storage** | A small store inside the visitor's browser. Remembers things on that device only; the server never sees it. |
| **Cookie** | A small piece of data the browser sends back to the server on every visit. We don't plan to need any. |

## How the work is organised

| Term | Meaning |
|---|---|
| **Product owner** | The person who decides what gets built and in what order, and accepts the result. |
| **Vision** | One paragraph saying why the product exists, who it is for, and what success looks like. |
| **Epic** | A big theme of work, made of several stories — e.g. "the word engine". |
| **User story** | A small feature written from the user's side: *"As a visitor, I want … so that …"*. |
| **Acceptance criteria** | Checks that decide whether a story is finished — written so anyone can test them. |
| **Backlog** | The ordered list of everything we might build. |
| **MVP** | *Minimum viable product*: the smallest version worth putting in front of people. |
| **Spike** | A short experiment to answer a technical question. Its result is knowledge, not shipped code. |
| **Kanban board** | Columns of cards showing where each piece of work is (Backlog → Done). |
| **Definition of Ready / Done** | The checklists a story must pass to start, and to finish. See [process.md](process.md). |
| **Decision record (ADR)** | A short file explaining one technical choice: options, trade-offs, decision. |
| **Effort sizes (S / M / L)** | Rough size of a piece of work, compared to other pieces — not hours. |

## Git and GitHub

| Term | Meaning |
|---|---|
| **Repository (repo)** | The project folder plus its full history of changes. |
| **Commit** | One saved change, with a message describing it. |
| **Branch** | A parallel line of work. Changes are made on a branch so `main` stays working. |
| **main** | The branch that holds the accepted, live version. |
| **Pull request (PR)** | A request to merge a branch into `main`. It is where changes are reviewed and approved. |
| **Merge** | Bringing a branch's changes into `main`. |
| **Issue** | A card on GitHub describing one piece of work — a story, a spike, a bug. |
| **Squash merge** | Merging a pull request as one single commit on `main`, however many commits the branch had. |
| **Ruleset (branch protection)** | GitHub rules on a branch — e.g. "changes to `main` only through a pull request". |
| **Secret scanning / push protection** | GitHub checks every push for passwords and keys, and refuses the push if it finds one. |
| **Dependabot** | A GitHub bot that warns about (and offers fixes for) libraries with known security problems. |
| **CLAUDE.md** | A file in the repo that Claude reads at the start of every session — the project's standing instructions. |
