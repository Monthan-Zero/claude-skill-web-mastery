# Success Science — why sites convert (research-grounded)

The evidence base for design decisions. Cite these numbers when justifying choices.

## 1. First impressions are formed before reading

- **50ms studies** (Lindgaard et al., *Behaviour & IT*): visual-appeal ratings at 50ms correlate strongly with 500ms ratings. Judgment forms before a single word is read; global features dominate (dominant color, layout density, symmetry, image quality, familiarity).
- **Stanford Web Credibility Project** (2,684 participants): 46.1% of credibility assessments referenced *visual design*, not content; ~75% of users judge company credibility from website design.
- **Halo effect**: the first aesthetic judgment biases everything after it — perceived usability, trustworthiness, even content quality (aesthetic-usability effect).
- Practical: the above-the-fold screen gets ~57% of total viewing time. Design the first viewport as if it's the only one most visitors see — because it is.

## 2. Speed is a revenue feature

- Google/Deloitte: **+0.1s speed → +8.4% retail conversion, +9.2% average order value**.
- eBay/Deloitte: every **100ms of LCP delay ≈ −1.11% conversion**.
- Rakuten 24: meeting CWV thresholds → **+53.4% revenue per visitor, +33.1% conversion**.
- Product pages at 2s LCP convert **40–50% better** than at 4–5s.
- Thresholds to hit (75th percentile): **LCP ≤ 2.5s, INP ≤ 200ms, CLS ≤ 0.1**. Only ~42% of mobile sites pass all three — passing is a competitive edge, and mobile is ~62% of traffic.
- The usual killers: uncompressed hero images (compress BEFORE upload; WebP ~30% smaller than JPEG), unpreloaded fonts (CLS), autoplaying video, heavy JS.

## 3. Landing page anatomy (the converting sequence)

Order: **Hero → UVP → Benefits → Proof → Objections → CTA (again)**.

**Hero (above the fold)** must contain, without scrolling:
- Headline: the core benefit, comprehensible in <5s. Clarity over cleverness — "The marketer's art is not persuasion; it is clarity" (McGlaughlin).
- Subheadline: how it works / for whom, one or two sentences.
- One CTA, visually dominant, action verb ("Build your first set", "Start free") — never "Submit" or "Learn more" as primary.
- A proof whisper (user count, rating, citation) near the CTA.
- Product visual that shows the actual thing (real UI beats abstract art for products).
- **Message match**: hero wording mirrors whatever ad/link/search brought the visitor.

**Body**: benefits phrased as outcomes (not features); one idea per section; scannable (bold keywords, short paragraphs, generous space); social proof adjacent to every decision moment; objections answered where they arise (FAQ before final CTA); CTA repeated at natural commitment points (after proof, at end).

## 4. Trust is assembled from specifics

- Specific numbers beat adjectives ("9,713 exam items analyzed" > "research-backed").
- **Transparent pricing**: unexpected/hidden costs are the #1 abandonment cause (48%, Baymard). If pricing exists, make it findable in one click.
- Reviews/testimonials measurably raise completion (Baymard) — real names, specific results; fake-sounding praise backfires. Never fabricate.
- Security/credibility markers where money or data changes hands; recognizable badges outperform generic ones.
- Full footer (real entity, contact, legal pages) = subconscious legitimacy check.
- Flawless execution IS a trust signal: typos, broken links, default focus outlines, and unstyled states all read as "unsafe."

## 5. Laws of UX, applied

- **Hick's Law** — more options, slower decisions. Trim nav to 5–7 items; one primary CTA; progressive disclosure for depth.
- **Fitts's Law** — targets must be big and close. Tap targets ≥44px, generous spacing, thumb-reachable primary actions on mobile.
- **Jakob's Law** — users expect your site to work like every other site. Logo top-left → home; nav top; pricing in 3 columns; cart top-right. Break conventions only for atmosphere, never for mechanics.
- **Aesthetic-usability effect** — beautiful interfaces are *perceived* as more usable and are forgiven more. Polish pays twice.
- **Miller/chunking** — group content into 3–5 item clusters; long lists get categories.
- **Serial-position effect** — first and last nav items get the most attention; put "Pricing"/CTA at the ends.
- **Von Restorff (isolation) effect** — the one visually different item gets remembered: highlight exactly one pricing tier, one primary button.
- **Goal-gradient** — progress indicators accelerate completion (checkout steps, onboarding, streaks).

## 6. Conversion copywriting

- Clarity > cleverness; benefit > feature; reader's words > brand's words (mine reviews/support logs for voice-of-customer phrasing).
- Message hierarchy: a page should communicate its core promise from headings alone (squint test).
- Front-load value words in headlines; keep line length 45–75 chars; left-align body text.
- **Human-voice rules (standing)**: no em-dashes; no tricolon spam; no "not just X, but Y"; ban delve/unlock/seamless/empower/elevate/robust; vary sentence lengths (bursts of short); write to "you"; concrete nouns and numbers; read it aloud — if you wouldn't say it, rewrite it.
- Microcopy matters: button labels state the outcome ("Get my Master Set", not "Submit"); error messages say how to fix; empty states give the next action.

## 7. Forms & checkout friction

- Average checkout has 14.88 fields; best-in-class cuts to ~7. Every removed field lifts completion.
- Labels above fields; single column; inline validation on blur (not on submit); no surprise required fields; guest path before account creation; show total cost early.
- Ask for the minimum at signup; enrich later (progressive profiling).

## 8. Pricing page psychology

- Three tiers; middle tier visually isolated + "Most popular" (Von Restorff + social default).
- Anchor high tier first in reading order where upsell matters; unit-framing that maps to user value (credits = questions), and say plainly what a unit buys.
- Reduce risk at the decision point: free tier/trial, "cancel anytime", founding-rate honesty. Never fake scarcity.
- FAQ directly below pricing — objections peak there.

## Sources (primary)

Baymard Institute checkout/trust research · Stanford Web Credibility Project · Lindgaard et al. 50ms studies · web.dev CWV business-impact case studies (Rakuten, Vodafone, Cdiscount) · Deloitte/Google "Milliseconds Make Millions" · eBay speed studies · Laws of UX (Yablonski) · CXL/Unbounce landing-page research · MECLABS/McGlaughlin on clarity.
