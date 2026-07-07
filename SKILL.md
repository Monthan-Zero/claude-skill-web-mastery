---
name: web-mastery
description: Expert web design, conversion science, and Webflow mastery. Load for ANY website work — landing pages, marketing sites, Webflow builds, dashboards, pricing pages, redesigns, site audits, or "make it professional/premium" requests. Contains the success research (why sites convert), the Webflow execution playbook (native-first, Client-First classes, API gotchas), and the pre-ship QA protocol. Complements frontend-design (aesthetic direction); this skill covers what makes sites WORK and how to execute at expert level.
---

# Web Mastery — build sites that look expert and actually succeed

Built from deep research: Baymard Institute, Stanford Web Credibility, NN/g, the 50ms first-impression studies, Core Web Vitals business cases (Deloitte/Google, Rakuten, eBay), Laws of UX, Finsweet Client-First, Webflow's own performance guidance, and hard-won lessons from real Webflow API builds.

## How this skill relates to `frontend-design`

Load **both** for visual web work. `frontend-design` picks a distinctive aesthetic direction and escapes AI-slop defaults. **This skill** adds the other two thirds: the *success science* (conversion, trust, speed) and *expert execution* (Webflow techniques, QA). Direction from frontend-design, decisions from here.

## The ten operating laws (memorize; details in references/)

1. **You have 50 milliseconds.** Visual-appeal judgments at 50ms match 500ms judgments; 75% of users judge credibility from design alone. The first screen IS the brand.
2. **Clarity is persuasion.** Value must be understood in under 5 seconds. Benefit over feature, specific over vague, plain over clever. If a visitor must think, you lost.
3. **Speed is revenue.** +0.1s speed = +8.4% retail conversion; every 100ms of LCP delay ≈ −1.1% conversion. Compress images before upload. Treat performance as design.
4. **One primary action per view.** Every screen has exactly one visually dominant CTA; everything else is ghost/tertiary. Repeat the CTA at decision moments.
5. **Familiar beats clever (Jakob's Law).** Users spend their time on other sites; follow conventions for nav, logo→home, forms, pricing layout. Spend novelty budget on atmosphere, not mechanics.
6. **Friction is the enemy, uncertainty is the killer.** Most losses are unresolved doubt, not disinterest. Cut fields, cut steps, answer objections next to the CTA (FAQ), never hide costs (hidden cost = #1 abandonment reason, 48%).
7. **Trust is assembled from specifics.** Real numbers, real citations, transparent pricing, reviews near decisions, flawless typography. One typo or broken state costs more than any feature adds.
8. **Consistency reads as expensive.** Systems, not choices: one accent, strict spacing scale, one radius scale, tinted neutrals (never pure #000/#fff), two-part shadows. Amateur = assembled; expert = considered.
9. **Finish all six microstates.** Default / hover / focus-visible / active / disabled / loading — on every control. Designed focus rings. **No emoji as UI iconography — ever** (canonical amateur tell; also a standing user rule).
10. **Verify like a skeptic.** Never claim done without loading the real page: mobile overflow check, console, gate flows, published-string greps. Silence is not success.
11. **Never ship the statistical average.** AI builders converge on one recognizable page (formula hero, card-grid sections, pill everything, metronomic label→h2→grid rhythm) — and humans now see it instantly as "AI-made." Every build must pass the v0 test: vary section anatomy, break symmetry once per view, include one bespoke artifact. See `references/anti-ai-look.md` — this is a hard requirement, not a style preference.

## Standing user rules (Michael — apply always)

- **No emojis** anywhere in user-facing products.
- **No AI-copy tells**: zero em-dashes (use commas/periods, "|" in titles), no tricolon overload, no "not just X", no delve/unlock/seamless/empower/elevate. Vary sentence length. Read-aloud test. Second person, specific numbers.
- **Premium bias**: dark, considered, editorial; gold-on-ink for Menvel-family work. Expensive = restraint + finish, not effects.
- **Webflow native-first**: real Webflow elements + native styles (Designer-editable); custom code only where Webflow can't go (keyframes, pseudo, media queries, JS). Say what's native vs code.

## Workflow for any site build or audit

1. **Brief** (via frontend-design): direction, type pairing, palette, background, signature moment.
2. **Message architecture**: headline (benefit, <5s test) → sub → proof line → one CTA. Then UVP → benefits → proof → objections/FAQ → CTA again. Match entry-source wording.
3. **Build native-first** — see `references/webflow-mastery.md` for the class system, structure, and the API/MCP execution playbook with its gotchas.
4. **Copy pass**: human-voice rules above; every heading earns its size; scannability (bold keywords, short rows).
5. **Success pass** — see `references/success-science.md`: trust placement, CTA repetition, friction audit, pricing psychology, UX laws.
6. **SEO/perf pass**: unique title <60 + description <155 per page, one H1, OG data + 1200×630 image, JSON-LD, compressed WebP images, font preconnect + swap, alt text.
7. **QA + verify** — run `references/qa-protocol.md` in full. Publish, then curl/preview the LIVE site and check strings, mobile, console, and flows before reporting.

## References

- `references/success-science.md` — the research on what makes sites convert: stats, landing anatomy, trust, UX laws, copywriting, forms, pricing.
- `references/webflow-mastery.md` — Client-First classes, structure, interactions/GSAP, SEO/perf on Webflow, and the full MCP/API execution playbook with tested gotchas.
- `references/anti-ai-look.md` — the visual tells that make a site read as AI-generated and the escape moves. Run its self-test on every build.
- `references/qa-protocol.md` — the pre-ship checklist and live-verification procedure (includes the AI-look sweep).
