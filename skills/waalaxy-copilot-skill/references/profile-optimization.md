# LinkedIn Profile Optimization (Waalaxy method)

Audit and rewrite a LinkedIn profile so it converts the traffic a campaign drives to it. This is
**the base of the base** — the first thing to fix for any account, new or existing, before any
campaign runs.

The single most undersold lever in the Waalaxy methodology:

> **A weak profile can halve your acceptance rate — even with perfect targeting.**

The profile is the page prospects visit the moment your invitation lands, before they decide to
accept. Profile work is a **multiplier on every other campaign element**. Fix it first, or every
campaign runs at half its potential acceptance rate and burns prospect list for nothing.

Language: audit and deliverables in the **user's** language. Rewrites (headline, banner copy,
About) in the language of the **campaigns they run** — a French-prospecting user gets French copy.
Match the dominant campaign language; never mix.

---

## Where the profile shows up in the metrics

| Metric | Profile element that drives it | Good benchmark |
|---|---|---|
| **Acceptance rate** | Photo + headline + banner (the trio in the invitation notification) | 30–45% (50%+ recruitment) |
| **Reply rate** | About + Featured + story coherence | 8–25% (~14–15% "good") |
| **Conversion rate** | Services + Featured (lead magnets, case studies) + CTA links | tied to targeting fit |

> Profile failures cost you at the gate. Copy failures cost you in the conversation. Targeting
> failures cost you on conversion.

---

## Getting the profile content (LinkedIn URLs can't be fetched)

Never ask for the profile URL and never try to `web_fetch` a LinkedIn profile — LinkedIn blocks it.
Instead, ask the user to export the page:

> "LinkedIn blocks automated reading, so I can't open your profile from a link. Do this instead:
> open your LinkedIn profile in the browser → **right-click → Save As → Web Page, Complete (.html)**
> (or `Cmd/Ctrl+S`) → upload the saved `.html` file here. I'll read your photo alt text, headline,
> banner, About, Featured, Services and links straight from it."

Parse the uploaded HTML for each element below. If the file is missing a section (e.g. the banner
image, or Featured), say so and ask the user to describe it rather than guessing.

## Always ask for the website (source material for the rewrites)

Profile copy is only as sharp as the positioning behind it. Before writing any headline, banner, or
About, **always ask for the user's website**:

> "What's your website? I'll pull your value proposition, the problem you solve, and your
> differentiator from it so the profile tells the same story as your site."

- If the **Website Analyzer** already ran this session, reuse its four handoff inputs (value prop,
  pain, differentiator, champion) — don't re-ask.
- Otherwise fetch the site with `web_fetch` (websites are fetchable; only LinkedIn is blocked) and
  extract those four inputs before rewriting.
- If the user has no website, ask them for the value prop / who they help / differentiator directly,
  and leave `[placeholders]` for anything they can't give.

---

## The audit — walk the profile as a prospect, element by element

Working from the uploaded HTML (and the website inputs above), score each element below. Every
weakness ships with a concrete rewrite, never just "make it clearer." Never invent credentials,
clients, or metrics — use `[bracketed placeholders]` and tell the user what to supply.

### 1. Profile photo
First element in the invitation notification — a weak photo lowers acceptance independent of copy.
- ✅ Smiling, warm, face clearly visible, professional-but-approachable, good contrast/lighting,
  mid-distance from camera.
- ❌ Black & white (reads artistic, creates distance), party shots, extreme close-up or full-body,
  dark/muddy lighting, corporate stiffness.

### 2. Headline — the highest-leverage text element
Shows next to your name in the invitation notification, in search, and in "People you may know."

**Formula:** `[Who you help] + [Concrete result] + [Key differentiator]`
Equivalently: **"I help [WHO] to [WHAT] using [HOW]."**

A strong headline has all three:
1. **Specific WHO** — "wealth advisors" / "50–100 person finance directors", not "professionals" or "teams".
2. **Concrete outcome** — "eliminate 2h of manual reporting per week", not "work better together".
3. **A real differentiator** — "20 years in financial markets", "owning their client data".
   ("Innovative", "best-in-class", "AI-powered" don't count — every competitor claims them.)

Good: *"I help wealth advisors grow their business while staying independent and owning their client data."*
Bad: *"CEO & Founder at [Company]"* · *"Consultant in digital transformation"* · *"I help teams reset, refocus and thrive"* (job-title-only, buzzword cluster, vague verbs — all wasted prime real estate).

### 3. Banner — the expansion of the headline (the storefront)
A passing prospect must answer three questions from the banner alone, in a few seconds:
1. **What do you sell?** 2. **Who do you sell it to?** 3. **Why you, not a competitor?**

Must contain: a **declarative** value prop (not a rhetorical question), the specific problem you
solve (not the ultimate goal), social proof (clients / awards / testimonials), and **one** clear CTA.
Avoid: rhetorical questions, 2010-PowerPoint aesthetics, vague slogans ("Where innovation meets
results"), generic stock imagery, multiple competing CTAs, mixed sales+employer-brand purpose.

Banner CTAs that work — matched to a Featured asset: "Get the [X] checklist", "Take the [X]
assessment", "Read the [case study]", "Book a strategy call" (only if the rest of the profile earns it).

### 4. About — the same story, with proof
Structure:
1. State the WHO/WHAT/HOW in one paragraph.
2. Expand the specific problem and the daily pain it creates.
3. Add proof: case studies, named clients, concrete metrics.
4. End with a CTA matching the banner + Featured.

Avoid: career-CV chronology ("Started at X in 2010…"), generic mission statements, uncontextualized certification lists.

### 5. Featured — the self-serve path (one of the highest-converting surfaces)
Prospects often want to self-serve before talking. Featured is where that path lives.
- 3–5 **intentional** tiles with custom visuals, not random old post links.
- Lead magnets (guides, quizzes, calculators), testimonials/case studies as tiles, booking links,
  website link — each with a clear CTA image.
- CTAs mirror the banner CTA: one coherent path, not three competing offers.
- Common failure: empty, or filled with random old posts.

### 6. Services — the most under-used proof surface
Visitors here are further along. Fill it with named, specific client testimonials.

### 7. Links — anchor text matters
"Visit my website" is a wasted link. Use "Get the 7 Rules for [outcome]", "Take the Burnout
Assessment", "Book a Strategy Call". Each link matches a Featured asset + the banner CTA.

---

## The coherence rule (audit these three together)
The **headline** plants the claim → the **banner** expands it → the **About** proves it. If they
tell different stories, the profile reads as confused and the prospect bounces. When you change any
one, re-check the other two.

**Single objective:** the profile is sales OR employer-brand — never both. Trying to be both
dilutes conversion on both. Pick one and make every element serve it.

**3-second mobile test:** open the profile in incognito on mobile (most LinkedIn traffic is mobile).
From photo + headline + banner-top alone, can a stranger say who you serve and what you help them do?
If not, the storefront is failing.

---

## Diagnostic ladder (when a campaign misses benchmarks)
1. **Low acceptance (<30%) with sound targeting** → profile + invitation note. Pull the note first;
   then audit photo → headline → banner. (No-note typically lifts acceptance 10–50%.)
2. **Healthy acceptance but low reply (<5%) with sound copy** → About/Featured/Services: is there a
   coherent story and something of value to consume? Check headline↔banner↔About coherence.
3. **Reply fine but low close** → wrong segment; retarget (not a profile problem).

---

## Pre-launch checklist (profile + account warm-up)
Before the first invitation of any campaign:
- [ ] Photo: trustworthy, smiling, well-lit
- [ ] Headline: specific WHO + concrete outcome + real differentiator
- [ ] Banner: declarative value prop, single CTA, passes the storefront test
- [ ] About: same story as headline+banner, with proof, ends on a CTA
- [ ] Featured: 3–5 intentional tiles, not empty
- [ ] Services: shows named testimonials
- [ ] Links: descriptive anchor text matching banner + Featured
- [ ] Single objective (sales OR employer-brand)
- [ ] Account warmed up: 200–300+ connections, profile complete, some organic activity, groups/hashtags followed

A brand-new or dormant account gets restricted faster when automation starts. Warm-up is a
precondition, not optional.

## Re-audit cadence
- Before the account's first campaign — full review.
- Every 6–12 months — full re-audit ("does this still speak to my prospects?"). The ICP drifts.
- Quarterly — re-check headline (still matches current ICP?), banner CTA (still points to a live asset?), Featured (still relevant?).
- After any major positioning change — full rewrite.
- After an acceptance-rate dropoff with no other changes — full review.

---

## LinkedIn banner image prompt generator (ChatGPT / Gemini)

After rewriting the banner **copy** (section 3 of the audit), offer to generate the banner **image**:
a ready-to-paste prompt for an AI image generator. Image models can't reliably output LinkedIn's
4:1 (1584×396) aspect ratio, so the proven workaround is to generate a **16:9 landscape** image with
large blank white top/bottom margins, then center-crop it to 4:1 — everything important lives in a
central strip that survives the crop.

**Prerequisites — pull these before writing the prompt:**
- **Design system** from the **Website elements** block in `prospecting-strategy.md` (colors, fonts,
  style, logo, art direction). If the website hasn't been fetched yet, fetch it now — the banner must
  be on-brand, so never invent brand colors. If a token is genuinely unavailable, say so and use a
  neutral professional palette, flagged as a placeholder.
- **Content** from the profile audit: the value proposition, the WHO/outcome/differentiator, and the
  single banner CTA.

Offer: "Want a ready-to-paste ChatGPT/Gemini prompt to generate this banner, on-brand with your
site's design system?" On yes, output the prompt below in one copy-paste code block, brackets filled.
The **layout rules are fixed** (they're what makes the crop work) — only the brand/content slots change.

```
Create a professional LinkedIn banner intended to be cropped later into the official LinkedIn banner
size (1584 × 396 px) for [company / domain].

IMPORTANT LAYOUT RULES
• Generate the image in a standard LANDSCAPE format (16:9).
• Do NOT try to make the artwork itself 4:1.
• Reserve the CENTER HORIZONTAL STRIP as the only content area.
• Leave LARGE PURE WHITE margins at the top and bottom.
• These white margins are intentional and will be cropped away later.

SAFE AREA
• Only place logos, headlines, illustrations, buttons and important visual elements inside the
  central horizontal strip.
• The central strip should occupy roughly the middle 35–40% of the image height.
• The top and bottom ~30% should remain almost completely blank white.

LINKEDIN PROFILE PHOTO
• Inside the central strip, keep the leftmost 320 px equivalent visually clean.
• Do not place text or logos there. Only subtle background graphics are allowed.
• Assume LinkedIn's circular profile photo will cover this area.

CONTENT POSITIONING
• Headline centered vertically within the safe area: "[banner headline — the value prop, declarative]"
• Supporting text underneath: "[one supporting line — the specific problem solved]"
• Call-to-action treatment (button or pill): "[single banner CTA]"
• Illustration or product visual on the right.
• Plenty of whitespace. Nothing important may touch the top or bottom margins.

BRAND / DESIGN SYSTEM (from the company website — match it exactly)
• Primary color: [#hex]   Secondary: [#hex]   Accent: [#hex]
• Background of the central strip: [#hex or "white to match margins"]
• Text color: [#hex]
• Typography feel: [heading font family / style], clean and legible
• Corner radius: [sharp / rounded / pill]
• Logo: [describe or "place the wordmark, [color], top-left of the central strip, after the photo zone"]
• Art direction: [mood + imagery style from Website elements]

STYLE
• Flat modern SaaS design • Clean geometric layout • Minimal • High-end • Professional
• Lots of whitespace • No unnecessary decorations

VERY IMPORTANT
Imagine that after generation, the image will be center-cropped to a 4:1 LinkedIn banner. Everything
important must already fit perfectly inside that future crop. Anything placed in the top or bottom
white margins should be considered disposable.
```

After the prompt, one line: tell the user to generate it, then center-crop to 1584×396 (the white
margins are the disposable part). Offer to adjust copy or art direction. Don't fabricate a logo or
metrics to fill the banner — use the real design system or leave a marked placeholder.

---

## Output structure (in the user's language)

1. **Snapshot verdict** — one line: is this profile ready to run campaigns, or is it leaking
   acceptance? Which element is the biggest leak?
2. **Element-by-element scorecard** — photo, headline, banner, About, Featured, Services, links.
   For each: ✅ / ⚠️ / ❌ + one line why.
3. **Rewrites** — new headline (2–3 options via the formula), banner copy + CTA, About skeleton.
   Then offer the **banner image prompt** (ChatGPT/Gemini) built on the site's design system.
   Use `[placeholders]` for facts you don't have and name what to fill in.
4. **Coherence check** — do headline → banner → About tell one story? Single objective? Passes the
   3-second mobile test?
5. **Prioritized fix list** — P0 (kills acceptance at the gate) → P1 (costs replies) → P2 (polish).
6. **Expected impact** — tie the top fix back to the metric it moves (e.g. "fixing the headline +
   photo is what stands between you and the 30–45% acceptance band").

Educate, don't self-critique. Explain *why* each element matters (which metric it drives), so the
user can maintain the profile themselves next time.
