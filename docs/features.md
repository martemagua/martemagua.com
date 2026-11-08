# Feature inventory

Step 3 of the [process](process.md): everything on the table, grouped into
*epics*. Nothing here is a promise. Step 4 sorts it into must / should / could /
won't and cuts the first release.

★ = suggested for the first release (to be confirmed in step 4).

## What the first release must get across

A visitor should understand within seconds that:

1. the page can be touched and played with, and
2. they can write in the *o mar tem ___* field, and what they write changes
   what the sea shows.

Everything marked ★ serves those two moments.

## Epics

### 1. Living sea ★

The flat, playful 2D sea from the prototype moves on its own: waves, kelp,
fish and bubbles. The sky follows the visitor's clock and shows a greeting
(*bom dia*, *boa noite*…) rather than numbers.

### 2. Invitation to play ★

Makes it obvious that the field is there to type in and that the sea reacts:

- the field stands out, and its placeholder cycles through example words
- a gentle nudge on the first visit
- a known word causes an immediate, visible change
- a "?" button that surprises you with a word

### 3. Word engine ★

Turns a typed word into something the sea has:

- accepts Brazilian and European Portuguese spellings, unaccented typing and plurals
- updates the *mar·tem·‹palavra›* headline
- adding a new word is one small, obvious change (vision: success for the code)

### 4. Unknown words: message in a bottle ★

Every word gets a response. A word the sea doesn't know yet goes into a
**message in a bottle** that drifts away across the water. This replaces the
prototype's floating letters, which we dropped.

### 5. Touch, tilt and fallbacks

- ★ Touch: ripples, popping bubbles, feeding the fish
- Tilt the phone and the water sloshes
- Mouse and keyboard still do everything

### 6. Things play together

Things in the sea react to each other and to their surroundings: fish chase
plankton, a boat bobs on the waves, light makes creatures glow. This is the
long-term fun, and it grows one word at a time.

### 7. Progress on the device

The sea remembers which words you have discovered, in local storage only.
Nothing leaves the visitor's device.

### 8. Word log and review pipeline

Shows which words people try, so we can decide what to add next.

**Decided: option B, anonymous unknown words.**

| Option | What is stored | Decision |
|---|---|---|
| A. No log | Nothing | Rejected: we would learn nothing |
| **B. Anonymous unknown words** | Only unknown words, as *word + count*. Single words of letters, at most 18 characters. No time, device or IP address | **Chosen** |
| C. B, but the visitor opts in | Same as B, only after a "yes" | Rejected: more UI, fewer words |
| D. Full log | Every word with time and device | Rejected: conflicts with *innocent and private* |

What option B means in practice:

- The page shows a one-line note in Portuguese saying new words are shared
  anonymously so the sea can grow.
- The server must not record visitors' IP addresses for this request. Web
  servers do this by default, so switching it off is part of the work.
- Someone could still type a name or something personal. The review step
  deletes those.

**Review pipeline:** a regular pass over the collected words.

1. **Collect.** Unknown words arrive in the log with a count.
2. **List.** Words are listed by count, with spelling variants grouped
   together (*conchas*, *concha*, *côncha*).
3. **Sort.** The product owner marks each word:
   - *candidate*: could become a thing in the sea
   - *later*
   - *no*
   - *delete*: personal or offensive, removed from the log
4. **Turn into stories.** Each candidate becomes a user story ("o mar tem
   polvo"), and goes on the board like any other story.

How the list is produced (by hand, a small script, or with Claude's help) is
decided when we write this epic's stories.

### 9. Sound

Off until the visitor turns it on. Sounds for touches, bubbles and new words.

### 10. Language and accessibility ★

- All visitor-facing text in Brazilian Portuguese
- Respects `prefers-reduced-motion`
- Visible keyboard focus
- Sound only after the visitor turns it on

### 11. Hosting and delivery ★

The domain, HTTPS, serving the site from the home server, and how a merged
pull request reaches the live site.

### 12. Speed ★

Runs smoothly on an ordinary phone and loads fast on mobile data.

## Later, or not at all

- Realistic 3D ocean, fluid effects
- Scrolling dive minigame
- English and German (later, where the jokes survive)
- Anything with accounts, scores or leaderboards (won't: see vision non-goals)
