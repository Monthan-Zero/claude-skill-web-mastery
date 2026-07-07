# Pre-Ship QA Protocol — run in full before calling anything done

Silence is not success. Every claim of "done" requires the checks below against the LIVE published site (or a faithful local mirror of it).

## 1. The AI-look sweep (see anti-ai-look.md)

- [ ] No two consecutive sections share the same skeleton (label → h2 → sub → card grid twice in a row = fail).
- [ ] At least one bespoke artifact on the page (annotated screenshot, custom diagram, typographic set-piece).
- [ ] Not everything is a rounded card; not everything is a pill.
- [ ] The v0 test: "could a one-line prompt have produced this hero / features / pricing?" — each needs one deliberate deviation.
- [ ] **Zero emojis** in UI (regex sweep the published HTML: `[\x{1F300}-\x{1FAFF}\x{2600}-\x{27BF}]`).

## 2. Copy sweep

- [ ] Zero em-dashes (including SEO/OG titles — use "|" or "·").
- [ ] No banned words: delve, unlock, seamless, empower, elevate, robust, "not just".
- [ ] Sentence lengths vary; read one section aloud — would a person say it?
- [ ] Headlines pass the 5-second value test; squint test: headings alone tell the story.
- [ ] Specifics over adjectives (numbers, sources, names).

## 3. Craft sweep

- [ ] No pure #000/#fff; neutrals share one temperature; ONE accent doing the work.
- [ ] Spacing on the scale; groups separated by more space than their contents.
- [ ] Contrast: body ≥4.5:1, large text/UI ≥3:1 (spot-check muted text on dark panels).
- [ ] All six microstates on every control: default/hover/focus-visible/active/disabled/loading.
- [ ] Designed focus rings visible on keyboard Tab (never browser-default, never removed).
- [ ] One clearly primary CTA per view; radius/shadow scales consistent.

## 4. Responsive & runtime

- [ ] 375px: `document.documentElement.scrollWidth === window.innerWidth` (no horizontal overflow).
- [ ] Grids collapse sensibly; tap targets ≥44px; nav usable on phone.
- [ ] Console: zero errors on every page.
- [ ] Animations: reduced-motion honored; nothing infinite without pause; transforms/opacity only.

## 5. Flows

- [ ] Auth/gate: test BOTH states (no session → gate with working sign-in/create buttons; session → dashboard renders with data: count rendered children, don't just eyeball).
- [ ] Every CTA routes where the funnel says (entry CTAs through the gate, not around it).
- [ ] Anchors (#section) land correctly under fixed navs; internal links resolve; no dead href="#" left as real UI.
- [ ] Forms: inline validation, error copy says how to fix, success state exists.

## 6. SEO / meta

- [ ] Per page: unique title <60, description <155, one H1, OG title/description (+1200×630 image when available).
- [ ] JSON-LD present and valid on key pages; alt text on meaningful images.
- [ ] No accidental "—" or emoji in titles; canonical/redirects sane.

## 7. Publish & verify (Webflow)

1. Publish (respect ~1/min rate limit; wait 90s between publishes).
2. `curl` the live URLs; grep for the NEW strings/classes you shipped (absence = old deploy still serving).
3. Visual check via local mirror if the preview browser is sandboxed: curl pages to files (absolute asset URLs render identically), serve statically, snapshot + resize + inspect; seed localStorage to test session flows.
4. Re-run sweeps 1–6 against what's actually live.
5. Report honestly: what verified, what's pending, what needs a human step (auth scripts, domain, plan limits).
