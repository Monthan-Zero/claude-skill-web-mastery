# The Anti-AI-Look — making sites read as human-designed

AI builders (v0, Lovable, Bolt) and LLM-generated UIs converge on the *statistical average* of web design — heavily weighted toward shadcn/ui and SaaS-template training data. Humans now recognize that average on sight. A site that triggers the recognition reads as cheap, templated, and untrustworthy, no matter how clean it is. This file is the tells list and the escape moves.

## Why it happens

LLMs don't make design decisions; they predict the most likely layout for "a modern SaaS landing page." The result is always the same page. Avoiding it requires deliberately choosing against the statistical default at several visible points.

## The visual tells (spot them, then kill them)

1. **Metronomic section anatomy** — every section is: small eyebrow label → big heading → one-line sub → grid of cards. Repeated five times down the page. This is the layout equivalent of uniform AI sentence rhythm, and it's the single biggest tell.
2. **Card-grid everything** — equal-sized rounded boxes with 1px borders and identical padding for features, testimonials, stats, pricing, steps. Gray card, subtle border, small icon, bold line, muted line.
3. **Pill everything** — fully-rounded (999px) buttons, badge chips, tag pills scattered across every section. The badge-pill language is the shadcn signature.
4. **The formula hero** — eyebrow badge + two-line headline with one gradient/italic word + sub + two buttons (solid + ghost) + floating tilted product card + radial glow. Statistically *the* most likely hero; instantly recognizable.
5. **Icon-emoji rows** — emoji or generic line-icons at the top of every card.
6. **Perfect symmetry, zero risk** — everything centered, every grid balanced, no element ever crosses a boundary, no scale surprises.
7. **No artifacts of a human hand** — no bespoke graphic device, no real product imagery, no texture, no typographic play, nothing that took a person an afternoon.
8. **Stock gradients** (purple/cyan), glassmorphism blur cards, dotted-grid backgrounds.
9. **"Coming soon" chips and generic empty states** sprinkled like confetti.

## The escape moves

- **Vary section anatomy on purpose.** Across a page, no two consecutive sections should share a skeleton. Rotate between: editorial two-column prose · a real table · an oversized numbered list · full-bleed image or artifact · a single centered statement · a dense index/spec block. If the label→h2→grid pattern appears twice in a row, redesign one.
- **Replace half the card grids.** Features as a numbered index list with hairline rules; evidence as footnoted prose with citation superscripts; stats as one huge typographic row, not three boxes. Tables read more expert than cards for comparisons (incl. pricing).
- **Asymmetry with intent.** 5/7 and 4/8 column splits, one element deliberately crossing a section boundary, oversized numerals or a headline word set at display scale as a graphic. Establish the grid, then break it in exactly one place per view.
- **One bespoke artifact per site.** Something a template couldn't ship: a drawn diagram, an annotated product screenshot, a custom chart, a stamp/seal/monogram, a specimen-style type block. This single element does more anti-AI work than any amount of polish.
- **Kill the pill.** Pick a radius stance that isn't 999px-everything: squared or 6–10px buttons with real presence. Chips/badges only where they carry information, never decoration.
- **Real product, real numbers, real names.** Screenshots of the actual UI, actual statistics with sources, specific dates and quantities. Vague = template; specific = made by people who know the thing.
- **Texture and print details** (used sparingly): paper grain, hairline rules, running headers, footnote markers, small-caps, tabular numerals, an index motif. Print heritage reads human because AI defaults don't have it.
- **Type does the branding.** A display face with character (not Inter/defaults), used at extreme sizes with tight leading, mixed with a utility face. A memorable headline setting beats any hero illustration.
- **Photography/art direction** if imagery is used: consistent treatment (duotone, grain), never stock-obvious, never AI-slop illustrations.

## The self-test

Before shipping, ask: **"Could v0 have produced this from a one-line prompt?"** Check each: the hero, the features section, pricing, the footer. If yes for any, that section needs one deliberate deviation (anatomy, asymmetry, artifact, or type move). Also run the copy tells (see success-science.md §6) — visual and verbal AI-ness compound each other.

## Worked example (self-audit of a real build)

A dark, gold-accented site with good craft still read "AI" because: every section followed label→serif-h2→sub→card-grid; features/evidence/pricing/steps/modes were ALL card grids; buttons and chips were all pills; the hero was the formula (eyebrow + 2-line headline + italic accent word + 2 buttons + tilted floating card + radial glow). The palette and fonts were distinctive — the *layout rhythm* was the tell. Fixes applied: features → numbered index list with hairlines; evidence → footnoted prose block; stats strip → one oversized typographic row; pricing → comparison table; hero card → annotated product screenshot; radius stance changed; one section deliberately broke the container.

**Rule of thumb: distinctiveness lives in layout variety and bespoke artifacts, not in color and fonts alone.**
