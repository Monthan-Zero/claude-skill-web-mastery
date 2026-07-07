# Webflow Mastery — expert execution playbook

How professionals build in Webflow, plus the tested API/MCP playbook with every gotcha hit in real builds.

## 1. Class system (Client-First, distilled)

The industry-standard convention (Finsweet Client-First). Rules:

- **Two class types.** *Utility* classes = global property bundles, **no underscore** (`text-size-large`, `background-color-primary`). *Custom* classes = component/page-specific, **underscore joins the folder and element** (`hero_content-wrapper`, `pricing_card-title`).
- **Names are sentences for strangers**: no abbreviations, no shorthand, general → specific (`team-list_headshot-wrapper`). Anyone should know what a class does from its name alone.
- **Variants use `is-` combo classes** on top of a base (`button is-brand`, `card is-featured`). A combo only ever rides its base.
- **Never deep-stack utilities** (3+ classes on an element). Un-reorderable in Designer, slow to edit, fragile. When styling gets specific, mint a custom class instead.
- **Canonical page skeleton**: `page-wrapper > main-wrapper > section_[name] > padding-global > container-large > padding-section-large`. Spacing lives in wrapper/utility layers, not smeared across content classes.
- One naming convention across every project = 75% faster handoffs (Finsweet's measured result).

## 2. Native-first, code as garnish

- Everything expressible as a Webflow style SHOULD be one (Designer-editable, canvas-visible). 
- Reserve custom code for what Webflow styles can't hold: `@keyframes`, pseudo-elements (`:before/:after` content), `@media` fine-tuning, `:focus-visible`, complex selectors, CSS variables, and JS.
- **Three code layers, used deliberately**: site head (fonts, tokens, global hovers/focus, shared keyframes, global JS objects) · page head (page-specific keyframes/media/clamp sizes) · page footer (page JS/data wiring). Keep each slim; state clearly what lives where.
- Components/Symbols for anything used twice (navs, footers, cards); style once, reuse by name.

## 3. Interactions & motion

- Prefer **transform + opacity** animations only (GPU-cheap); avoid animating layout properties (width/height/top). `will-change: transform` sparingly.
- Keep the *changed pixel area* small — the bigger the repaint rectangle, the worse mobile performs.
- Webflow's GSAP-powered interactions (2025+) natively cover staggers, SplitText, ScrollTrigger, custom easing; scope interactions to components so motion travels with reuse. Hand-written GSAP only for orchestration beyond the panel.
- **One signature moment** (a staggered hero reveal) beats scattered hovers. Micro-interactions 120–200ms; entrances 200–400ms ease-out; nothing infinite without a pause/skip; always honor `prefers-reduced-motion`.

## 4. Webflow SEO & performance

- **Compress images BEFORE upload** (the #1 LCP killer is a 5MB source even though Webflow serves WebP). Hero images ≤ ~250KB; meaningful alt text; below-fold lazy-loads by default — don't lazy-load the LCP image.
- Per page: unique title <60 chars (keyword early), description <155, exactly one H1, semantic heading order, OG title/description + **1200×630 OG image**, JSON-LD via page settings (Organization/WebSite/Product/FAQ as fits).
- Fonts: preconnect + `display:swap`; limit families/weights; variable fonts where possible.
- Hygiene: delete unused classes/interactions (Style Manager cleanup), custom 404, 301 redirects on any slug change, canonical domain (www vs non-www) set once.
- Webflow gives clean semantic HTML, CDN, SSL, sitemap, minification for free — don't undo it with bloated embeds.

## 5. API/MCP execution playbook (hard-won, all tested)

Building headless via the Webflow MCP/Data API:

- **`data_whtml_builder`** turns HTML+CSS into REAL native elements + styles:
  - HTML must have **exactly one root element**.
  - `css` param accepts **single-class selectors only** — no descendant (`.a b`), no pseudo, no `@media`, no keyframes. Those go in head-code layers.
  - Class names in later inserts **bind to existing site styles** (styles are site-scoped) — define shared classes once, reuse by name with no `css` param.
  - `id` attributes in the HTML survive to published output (safe to wire JS against).
- **`update_style`** edits native styles, but Webflow stores border colors per side: setting `border-color` does NOT override existing `border-top-color` etc. — **set all four sides explicitly**.
- **Plain div/blocks reject `set_text`** (only text-type elements accept it). To change a div's text: whtml-insert a replacement `after` it, then `remove_element` the old one.
- Get element ids via `query_elements` (filter by style/tag/attribute; `scope_element_id` to search within; `return_parent` for ancestors).
- **Publish rate limit** ≈ 1/min — batch changes, publish once, wait ~90s before republishing.
- **Sitemap include/exclude API requires a paid site plan**; JSON-LD works via `bulk_update_pages_schema_markup` on any plan.
- **ALWAYS verify after publish**: `curl` the live URL and grep for new strings before telling anyone it's done. Webflow deploys take ~30–90s.
- **Visual QA trick**: preview browsers sandboxed to localhost can't open the live site — `curl` the published pages to local files (asset URLs are absolute, so they render pixel-identical), serve statically, then snapshot/inspect/resize there. Test JS flows by seeding localStorage before loading the mirrored page.
- Freeform head/footer code via `set_site_freeform_code` / `set_page_freeform_code` — writes replace the WHOLE block; always re-send complete content.

## 6. Auth / gating pattern (marketing site + external app)

- Marketing site = Webflow; the app lives elsewhere (e.g., Cloudflare). **Route every entry CTA through the gate page** (`/account`), never link the raw app URL from public pages.
- Session stub pattern: a tiny global (`window.X = {session(), signIn(), signOut()}`) in site head; gate page shows sign-in vs dashboard by session; purge legacy/demo session shapes on load so stale states can't haunt users.
- Hosted-auth providers (VaultVision et al.) typically bounce back with a hash (`#auth_login`) that THEIR site script must catch — detect the hash and show an honest "setup pending" note if the script isn't installed yet, never a silent dead-end.
