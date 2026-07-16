# Website Analyzer — positioning & messaging teardown (Fletch method)

Analyze a B2B/SaaS website's positioning & messaging against the Fletch PMM framework, then
hand back a prioritized fix list. Built on a B2B product-marketing agency's methodology — every
critique cites a named framework, so it reads as coaching, not opinion.

This module has **two jobs inside the Copilot**:

1. **Sharpen the site** — tell the user exactly what's unclear about their positioning and how
   to fix it (the standalone deliverable).
2. **Feed the prospecting engine** — the value proposition, pain, differentiator and champion
   surfaced here are the same inputs Step 1 (targets) and Step 4 (sequences) need. When the user
   goes on to build targets or messages, reuse what this analysis already established. Don't
   re-derive the value prop from scratch.

Analyze hard, but every critique ships with the fix. The goal is a clearer site and a sharper
prospecting angle — never just to make the founder feel bad. Follow the Copilot's output
discipline: educate (why this is unclear, which framework it violates), never self-critique.
Default voice: direct, specific, constructive. This is not a "roast" — keep it professional and
useful. Match the user's language.

---

## Workflow

### 1. Get the page content
- Fetch the URL with `web_fetch` — ask for the verbatim hero headline + subhead, every section
  headline, CTAs, nav labels, and any "trusted by" logos.
- If the homepage is thin, fetch one more page (pricing, product, about).
- If given screenshots or pasted copy, work from those directly.
- If nothing is fetchable, ask the user to paste the hero copy + section headlines.
- Note the apparent category, target customer, and growth model (PLG vs sales-led) — these change
  what "good" looks like.

### 1b. Extract the design system (light theme) — always
On every website fetch, also pull the **light-theme** design system and store it under
**"Website elements"** in `prospecting-strategy.md` (see the template). This is what lets the profile
module generate an on-brand LinkedIn banner later. Extract from the HTML/CSS, inline styles, CSS
variables (`:root`), `<meta name="theme-color">`, logo files, and any obvious brand tokens:

- **Colors** (as hex): primary, secondary, accent, background, text. Prefer the light theme; if the
  site is dark-only, capture that and note it.
- **Fonts:** heading family, body family (from `font-family` / Google Fonts / `@font-face`).
- **Corner radius** tendency (sharp / rounded / pill) and **visual style** (flat modern SaaS,
  gradients, 3D, illustrated, photographic…).
- **Logo:** URL or a short description (mark/wordmark, colors).
- **Art direction:** 1–2 lines on mood, imagery style, decoration level.

If a value can't be determined, leave it blank rather than inventing a hex. This block is reused by
the Profile Optimization banner generator — don't guess brand colors.

### 2. X-ray the messaging (the core move)
For the **hero** and every **section headline**, label each line with its messaging element(s),
then run the diagnostics below.

Never invent product facts. If a rewrite needs a detail you don't have, leave a
`[bracketed placeholder]` and tell the user what to fill in.

### 3. Deliver the analysis
Use the output structure at the bottom of this file.

---

## The 6 Messaging Elements (the atomic unit of every critique)

Every headline/section says one or more of these. To audit, label each line with its element(s).

| Element | Color | Question it answers |
|---|---|---|
| 🟪 Product Category | purple | What is the product? (the "shelf" it sits on) |
| 🟨 Target Customer / Persona / Company Type | yellow | Who is it for? (role/team + firmographics) |
| 🟫 Use Case | brown | What is the persona trying to do with it? |
| 🟥 Problem | red | What pain/limitation do they hit doing it the old way? |
| 🟧 Capability | orange | What can a user now DO? (the "unlock") |
| 🟩 Feature | green | What technically powers the capability? |
| 🟦 Benefit | blue | What's the outcome/state-change? |

Rule of thumb: lead with **Capability** (+ Category + Persona). Benefits and Features only land
*after* the visitor knows what the product is and does.

## Five Layers of Messaging (meet lower needs first)

Bottom → top. You cannot lead with the top until the bottom is established.
1. **Product Category** — "What is it?"
2. **Problem** — "What problem does it address?"
3. **Capabilities** — "How does it solve it?"
4. **Features** — "What powers that?"
5. **Benefits** — "What value does that give me?"

Skipping to benefits without the basics: (1) obfuscates what the product does, (2) lengthens the
customer journey, (3) makes you sound like you're bullshitting.

## Choosing the Hero Anchor (decision tree)

All 6 elements must appear *somewhere* on the homepage; the question is what to LEAD with.
- **Category mature or immature?**
  - **Mature → differentiating on product or market?**
    - Product → set of features → **Anchor on CATEGORY** (The Browser Company: "Get excited about your web browser.")
    - Product → one feature → **Anchor on FEATURE** (Nokia: "1 phone. 5 cameras.")
    - Market → **Anchor on PERSONA** (Canva: "The design tool for people who aren't designers.")
  - **Immature → one big problem or a collection of small ones?**
    - Collection → **Anchor on CAPABILITY** (Uber: "Push a button, get a ride.")
    - One big problem → elimination vs outcome?
      - Elimination → **Anchor on PROBLEM** (Loom: "Loom on. Meetings off.")
      - Outcome → **Anchor on BENEFIT** (Butter Payments: "Increase top-line ARR by 5%…")

### Hero must answer ONE question: "What is the product / what is it for?"
If the hero doesn't establish "the plot," the rest of the page won't make sense — the visitor is
dropped into Act 2 and stays confused. Visitors already agreed to read by landing; heroes don't
need to be "attention-grabbing," they need to be **clear**. Clarity > cleverness.

### Stack messaging elements (don't write a cute 3-word tagline)
Stack to maximize clarity, stop before it's hard to scan. Canva progression:
- Category+Persona: "The design tool for non-designers."
- +Capability: "…Create your next poster, business card, social post, or save-the-date"
- +Feature: "…with 100s of editable templates."

### "X For Y" template (anchored on one persona)
`[Product Category] for [Persona]` + capability (the unlock) + key feature (what powers it).

### Infomercial test — in 5 seconds the hero should convey
what it is · what it does · what problem it solves · when I'd use it · how I'd use it · why I'd use it.

## The 4 Most Common Homepage Mistakes (+ fixes)
1. **Too Many Messages** — 20+ features/benefits stuffed in. Fix: top 3 value props; rest to sub-pages.
2. **Divergent Product Categories** — multiple category concepts ("AI writing assistant" + "content
   platform"). Fix: pick ONE category for the homepage.
3. **Impenetrable Wall of Benefits** — leading only with outcomes ("10x your ROI!", "Save time!").
   "But what IS it???" Fix: lead with capabilities; benefits come after what + how.
4. **Vague Capabilities** — "Streamline your workflow!", "Optimize your operations!". Fix: name a
   concrete action the customer can picture doing.

## Write for the champion
Not the C-suite, not the end user — the **champion** in the middle (Manager / Director / VP): close
enough to feel the pain, senior enough to convene stakeholders. Exceptions: genuinely C-suite
products, and PLG where the end user IS the champion.

## Two undifferentiated phrases to ditch
- **"Single source of truth"** — everyone says it.
- **"Easy-to-use"** — no one believes you about your own UX; let testimonials say it.

## Differentiation — 4 ways
1. **Price** — undercut an expensive leader.
2. **Product** — a true 10x (not 2x). "Better UX" is NOT 10x.
3. **Distribution** — reach customers faster (PLG/freemium vs top-down).
4. **Segmentation** (most accessible) — own an underserved segment, build the perfect product for them.

### Differentiation Canvas (Old Way vs New Way)
- **Old Way**: Current Solution(s) + Weakness + Struggling Moment (specific enough to mark on a calendar).
- **New Way**: Product Category + Capability + Feature + Benefit.
- Mirror images: Weakness ↔ Capability, Struggling Moment ↔ Benefit. **Capability + Feature = your biggest differentiator.**

## Problem Section (most sites skip it — big differentiation opportunity)
- **Main problem** stated with the competitive alternative (your POV on why current tools fall short).
- **3 sub-problems**, each staging one of your differentiated features.

---

## The scorecard — count elements, grade vs the sweet spot

| Element | 👍 Sweet spot | 👎 Bad |
|---|---|---|
| Personas | 1–2 | 0 (no one self-identifies) or 3+ (too broad) |
| Problems | 1–3 | 0 (no one cares) or 4+ (confusion) |
| Product Category | 1 | 0 (no frame of reference) or 2+ (confusion) |
| Features | 1–5 | 0 (no believability) or 6+ (people stop caring) |
| Capabilities | 1–3 | 0 ("why'd you build this?") or 4+ (muddled) |
| Benefits | 1–3 | 0 (no payoff) or 4+ (confusing) |

### Grading bands
- **A** — Hero answers what/who/why in <5s, right anchor, has a problem section, differentiates
  clearly, all counts in the sweet spot.
- **B** — Clear what it is; minor element gaps or one overflow; differentiation a bit soft.
- **C** — You can eventually figure out what it is, but it leads with benefits/vagueness; no problem
  section; too many messages.
- **D** — Wall of benefits or vague capabilities; can't tell what the product actually does.
- **F** — Tagline-only hero, divergent categories, buzzword soup.

---

## Output structure (use these exact sections, in the user's language)

### 1. Verdict
One paragraph: the single biggest thing making this page unclear + a letter grade (A–F).

### 2. Hero teardown
- Quote the **actual hero** (H1 + subhead) verbatim.
- X-ray it: label each phrase with its messaging element(s).
- Diagnose: which of the 6 elements are present, which are missing, what it leads with, is that
  the right anchor (run the decision tree)? Does it pass "what is this / who's it for" above the fold?
- **Rewrite it.** 1–3 concrete options using a named template. Show the stacked version.

### 3. Section-by-section
Top to bottom. For each section: quote the headline → what it's doing wrong (or that it's missing,
e.g. no problem section) → the fix. Check feature sections cover Problem→Capability→Feature→Benefit.

### 4. The scorecard
Reproduce the element-count table with their actual counts vs the sweet spot + a verdict per row.

### 5. Prioritized fix list
Ranked, each line = **[P0/P1/P2]** Problem → *(framework it violates)* → the fix.
- P0 = visitors don't know what the product is / who it's for.
- P1 = clarity/differentiation leaks that cost conversions.
- P2 = polish.

### 6. One thing they nailed
End on a genuine strength — keeps the analysis fair and credible.

### 7. Prospecting handoff
Close with the clean inputs this analysis produced, ready to carry into targeting and messages:
- **Value proposition** (one sharp line)
- **Primary pain** solved
- **Sharpest differentiator** (Capability + Feature)
- **Champion** (the middle-manager buyer to prospect)

Then ask: "Want me to turn this into LinkedIn targets and an outreach sequence?" — if yes, hand
these four inputs into Step 1 / Step 4 instead of re-reading the site.

### 8. AI-tool rebuild prompt (offer when the site looks AI-generated)
Many Waalaxy customers build their site on an AI website builder. If the site looks generated by
one, the fastest path to shipping the fixes is a prompt the user pastes straight back into that tool.

**Detect the likely builder** from signals in the fetched page — meta generator tags, class-name
patterns, script/asset domains, footer "Made with…" badges:
- `v0.dev` / Vercel → **v0**  ·  `lovable.dev`, `gpteng` → **Lovable**  ·  `bolt.new` / StackBlitz → **Bolt**
- `.framer.website`, Framer badge → **Framer (AI)**  ·  `webflow.io`, wf- classes → **Webflow**
- `durable.co` → **Durable**  ·  Wix ADI, `wixsite.com` → **Wix**  ·  generic React/Next with no CMS → assume a code-gen tool (v0/Lovable/Bolt)

If the builder is unclear, **ask once**: "Did you build this site with an AI tool (v0, Lovable, Bolt,
Framer, etc.)? I can package the fixes as a prompt you paste straight back in."

**Then offer:** "Want a ready-to-paste prompt for [tool] that applies these fixes?" On yes, generate
the prompt below. Deliver it in one copy-paste code block, written in **English** (AI builders parse
English instructions most reliably) unless the site's own copy is in another language — then match it.

**Prompt template to generate:**

```
You are editing my existing marketing website built with [TOOL]. Keep the current design system,
layout, components, and brand — change COPY and SECTION STRUCTURE only, per the positioning fixes
below. Do not invent product facts; where a claim needs a detail I haven't given, insert a clearly
marked [PLACEHOLDER] instead of guessing.

Context:
- What we sell: [category]
- Who it's for (champion): [persona]
- Core value proposition: [one line]
- Primary pain we solve: [pain]
- Sharpest differentiator: [capability + feature]

Apply these changes:

1. HERO — replace the current headline "[verbatim current hero]" with:
   Headline: "[rewritten stacked hero]"
   Subhead:  "[rewritten subhead]"
   (Reason: [framework — e.g. hero was a wall of benefits; now leads with capability + persona].)

2. [Add a PROBLEM section after the hero / rewrite section X / remove divergent category Y / …]
   — for each P0 and P1 fix from the analysis, one numbered instruction: what to change, the exact
   new copy, and a one-line reason.

Constraints:
- Keep it to the top 3 value props; move anything extra to sub-pages.
- One product category on the homepage. One primary CTA.
- No "single source of truth", no "easy-to-use", no unproven ROI numbers in the hero.
- Preserve all existing images, styling tokens, and navigation unless a fix explicitly requires a change.
```

Fill every bracket from the analysis you just produced — pull the P0/P1 items from the fix list, the
verbatim hero from the teardown, and the four handoff inputs. Ship only the fixes the user has facts
for; leave `[PLACEHOLDER]` for the rest and list what they need to supply. Never fabricate metrics or
customers to make the prompt look complete.

---

## Rewrite playbook (reach for these when proposing fixes)
- **Hero won't say what it is** → stack: `[Category] for [Persona]. [Capability] with [Feature].`
- **Wall of benefits** → replace the lead with the capability the visitor can picture; demote the benefit.
- **Vague capability** → name the concrete action ("turn product usage into error-free bills in real time").
- **No problem section** → add one: main problem via the competitive alternative + 3 sub-problems.
- **Divergent categories** → pick the single clearest category; move the rest to sub-pages.
- **Too many messages** → cut to the top 3 value props.
- **"Single source of truth" / "easy-to-use"** → delete; replace with a specific capability, move UX to a testimonial.
- **Written for C-suite or end user** → re-target the champion (Manager/Director/VP).
- **ROI-numbers-as-hero** → push hard ROI far down; lead with what the product does.
