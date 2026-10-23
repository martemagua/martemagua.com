# 0001 — Record technical decisions in this folder

- **Status:** Accepted
- **Date:** 2026-10-23

## What we had to decide

This is a learning project: the product owner wants to be able to explain why
the site is built the way it is. Decisions made in chat get lost; code shows
*what* was chosen but never *why*.

## Options

| Option | Good | Bad |
|---|---|---|
| Keep decisions in chat | No effort | Lost after the conversation; impossible to look up |
| Explain in code comments | Close to the code | Scattered; doesn't show the options we rejected |
| One short file per decision in `docs/decisions/` | Easy to find, shows options and trade-offs, reviewed like any other change | A few minutes of writing per decision |

## Decision

Every real technical decision gets a short record in `docs/decisions/`, using
the template.

## Why

Principle 5 of the vision — *easy to explain beats clever*. A record lets the
product owner explain a choice months later, and lets a future contributor
(human or AI) understand it before changing it.

## What it costs us

A few minutes per decision. Small choices that are easy to undo don't need a
record; the rule of thumb is "would we argue about this again in six months?"
