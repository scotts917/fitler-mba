# Fitler MBA — Program Canon

*The living design standard for the Fitler MBA program. Every session build consults this document; every cross-session decision lands in the changelog. If a rule here and a habit in a build chat disagree, the canon wins — or the canon gets amended, with a changelog entry.*

**Repo:** `scotts917/fitler-mba` · served via raw CDN (`raw.githubusercontent.com/scotts917/fitler-mba/main/`). GitHub Pages is sandbox-blocked in build chats; the raw CDN is allow-listed.

> **Provenance note (2026-08-04):** Canon v1 was drafted during S04 prep (July 2026) but never pushed to the repo. This is a reconstruction from the conversation record and the shipped S04/S05 decks, current through the S06 scoping decisions. First committed version.
>
> **Provenance note (2026-09-28):** The canon was not updated during the S07 and S08 build cycles. The S06–S08 index rows and continuity entries below were backfilled from build-chat records during the S09 post-mortem. Items marked *(confirm)* need Scott's check.

---

## 1. Program identity

- **What it is:** a 20-session, AI-accelerated entrepreneurship program for Fitler Club members, meeting biweekly on Tuesday evenings (60–90 min; demonstrated envelope 90–150 — S09 ran to 8:30 with the room staying voluntarily). YC-meets-Wharton voice: practitioner-driven, framework-rigorous, zero academic throat-clearing.
- **The cohort:** ~32 mid-career operators and founders (roughly a third active founders/owners), **skewing heavily toward services businesses**. Sharp practitioners **new to structured entrepreneurship frameworks** — not framework-ignorant, not Wharton-fluent. Calibrate everything to that band.
- **Primary failure mode to design against:** confirmation-seeking and solution-first thinking.
- **Facilitator:** Scott Sill — program designer, builder, facilitator. Performs best in **reactive/live mode**, not scripted lecture.
- **Live-example guardrail:** Torev Motors (Scott's board company) may be used only with **public positioning** — no non-public information, ever. Standing rule against public strategic analysis of Torev; AI-block demos use program companies or the session case instead.
- **Real-company case guardrail (S09+):** Éclat Chocolate founder Chris Curtin agreed in the S09 debrief to continue working with the class. **He does not want detailed financial disclosure.** Any Éclat financial figure on a slide, handout or workbook is a clearly labeled assumption built from public information and reasonable estimates — never presented or implied as Éclat's actual numbers, and never attributed to Chris. Non-financial content (products, customers, channels, gifting program, positioning) is fair game within what Chris shares. Scott's separate advisory work with Éclat stays separate from the class case.
- **Community platform:** self-hosted **Discourse** (threaded forum) at `community.fitlermba.com` — *not Discord; these are fundamentally different products*. Postmark for transactional email (`community@fitlermba.com`).

## 2. Hard rules (non-negotiable)

1. **48-hour final-deck rule.** The lecture deck is complete at least 48 hours before the session — for narrative/flow polish and so Scott teaches rested. (S03 post-mortem.)
2. **Participation beat every ~10 minutes** in teach sections — never clustered post-break. Live/reactive consistently outperforms scripted. Satisfy it *structurally* where possible (S04's predict-before-reveal makes every event a beat). (S03 post-mortem.)
3. **Structure before building.** Architecture is discussed and batch-locked before any code or slide work begins. Ask-before-build is the default posture.
4. **Session isolation + shared canon.** Each session's build lives in its own dedicated chat, bootstrapped by pasting this canon plus the session's handoff doc. Anything that outlives the session lands here, with a changelog entry.
5. **Benchmark hygiene.** No unverified industry figures on slides. If a number can't be sourced, it's framed as an explicit assumption to stress-test, not a market fact. ("Verified drag beats borrowed benchmark" — S05.) Applies with extra force to Éclat financials (§1).
6. **Source strips on every computation slide.** The exact statement lines feeding a ratio sit beside the math. The room never holds a balance sheet in memory. (S05.)
7. **Within-deck sequencing rule.** A slide may not reference material the deck hasn't yet introduced.
8. **No quiz dynamics that suppress participation.** Predict-before-reveal is doctrine; vote-before-reveal on material the room is still learning to read is not (S05 v1 "Red Light, Green Light" rejected). Quizzing invites conversation; grading kills it.
9. **Artifact access policy.** Students get artifact links *after* the session (on the homework slide), not during — predict-before-reveal requires one shared board.
10. **Cold-runnable outputs.** Decks, facilitator notes, and artifacts must be operable by a different facilitator with no verbal scaffolding.
11. **Post-mortem discipline.** After each session: capture delivery learnings, log durable decisions here.
12. **Anti-Squirrel protocol.** No chasing useful-but-non-urgent tooling while focused build work is in progress.
13. **Self-rating.** Outputs rated against a 9.5/10 bar with shortfalls named proactively — never polished over.
14. **Human voice on slides.** Slide copy must not read as AI-generated: plain operator voice, short lines, Scott's own phrasing from his notes wherever it exists. No turned phrases, stacked em-dashes, clever reversals, or "that is the whole…" constructions. (S08: two drafts rejected. S09: canvas-framework deck rejected as cold "AI language" that missed marketing's mission.)

## 3. Design system (locked)

### 3.1 Palette & type — current standard (S05+)

| Token | Value | Use |
|---|---|---|
| `--navy` | `#1B2A41` | Primary ground / display |
| `--navy-deep` | `#111D2E` | Page backdrop behind slides |
| `--ivory` | `#F7F3E9` | Slide background / reversed text |
| `--gold` | `#C9A227` | Accent, eyebrows, emphasis |
| `--gold-soft` | `#D9BC5F` | Accent on dark slides |
| `--ink` | `#22303F` | Body text |
| `--muted` | `#6B7684` | Secondary text |
| `--red` | `#B3402F` | Negative / warning figures |
| `--green` | `#2E7D5B` | Positive figures |

- **Display:** Cormorant Garamond (serif). **Body/UI:** Inter (sans). Full stacks with system fallbacks.
- **Numbers:** tabular figures (`font-variant-numeric: tabular-nums`) so columns align.
- *Drift note:* S04 shipped on the predecessor palette (`#1b2541`/`#f4efe4`/`#b0894e`). S05 tokens are the locked standard going forward; do not match the S04 file.

### 3.2 Presentation decks

- **Single-file self-contained HTML.** Assets base64-embedded. Zero runtime network deps beyond the Google Fonts link.
- **Navigation:** keyboard (arrows/space) + touch; fullscreen support; per-slide facilitator notes on the **N key** *(spec optional in practice — S05 and S06 shipped without N-key notes at Scott's direction; the requirement stands only when a deck must be cold-runnable by another facilitator)*.
- **BLUF structure:** the session opens with the payoff stated (McKinsey bottom-line-up-front), cashed out later in the deck.
- **Sparse-deck pattern (S09):** for discussion-led sessions, one headline + one visual per slide; talking points live in N-key notes; stories are told live, not printed. The deck is bookends; Scott is the payload.
- **Framework slides:** worked examples live *inside* the framework canvas cells — never in a detached strip below.
- **Slides are connective tissue** when a live artifact carries the teach; the deck frames transitions, it doesn't compete.
- **PDF export gotcha (S06):** the `html-to-pdf` skill captures slides in their *initial* state — step-reveal (`data-step`) content is invisible and per-slide counters unpainted. Generate PDFs from a **print variant** that pre-adds the `shown` class to every step and statically paints the counters before conversion.

### 3.3 Interactive teaching artifacts

- **Single-file HTML + vanilla JS** (tiny reactive core at most). CDN-hostable from the repo.
- **State discipline:** pure `compute(events, cursor)` core; rendering is a pure function of derived state; undo = decrement cursor + recompute.
- **No `localStorage`/`sessionStorage`** (unsupported in the claude.ai artifact sandbox). In-memory state; explicit export when persistence matters.
- **Workbooks (S06+):** Excel joins the standing artifact classes. Structure: assumptions tab → P&L → cash flow → valuation (+ annotations tab documenting formulas). Nothing hard-coded downstream of assumptions. Formulas verified independently (recompute in Python, compare). Financial-model color code: blue inputs · black formulas · green cross-sheet links · yellow fill on the key levers.

## 4. Facilitation doctrine

- **Facilitate mode:** the artifact is the answer key, not the lecture. Quiz the room before revealing.
- **Predict-before-reveal** applies to computations *and* concepts (e.g., moving "$10K today vs. $11K next year" until the room splits teaches a discount rate before naming it).
- **Elastic session design (S04/S06 lesson):** every deck ships with named **expansion joints** (stories/scenarios that absorb a quiet room) and **compression valves** (segments that collapse without pedagogical cost). Fixed-length decks caused S04's short landing; elasticity is the insurance.
- **Two-landing structure:** a complete payoff by the published 7:30 end for anyone who must leave, plus a designed overflow back-third. *Open question after S09:* the room stayed to 8:30 for the live workshop — decide whether the overflow is now the main event and how the end time is announced.
- **Live-workshop format (S09+):** teach segment first (~40 min, sparse deck), then a live build on the standing real case, whole room, Scott at the board, no slides. Real founder + real product + live build is the strongest format the program has run.
- **AI inside the workshop (S09+ direction):** analysis and plan development are done *with* AI in the room. The loop: the room makes each call → AI drafts from it → the room critiques and tags every claim F (observed fact) / A (assumption) / Q (open question) → repeat. The room decides; AI is the fast junior analyst whose work gets checked. One person drives the keyboard; prompts are loaded before the session; a pre-generated fallback output is on hand in case of latency or a bad run. AI claims about the case company are assumptions until the founder confirms them.
- **Standing AI block:** 15–20 min per session, demoing on program companies or the session case (never Torev). Merges into the live workshop when the workshop *is* the AI-driven build (precedent: S06 Act 2B; standard from S09).
- **Case vehicles (revised S09):**
  - **Éclat Chocolate (primary, real, S09+).** West Chester, PA; founder Chris Curtin. Chosen because it is real, easy to visualize, tasteable, and straightforward, with both direct-consumer and B2B (corporate gifting) motions that transfer to the cohort's own businesses. Governed by the real-company guardrail (§1): no detailed financial disclosure.
  - **Éclat financial work** (pro forma, unit economics, valuation, cap table) runs on an **"Éclat-shaped" assumptions model**: every input labeled as an estimate, the build method shown so the room can challenge it, and a standing caption that the figures are not Éclat's. The lesson becomes how to build defensible assumptions when the real numbers aren't available — which is exactly the founder's position before launch.
  - **Main Line Sports Institute (fictional, services counterpart).** Multi-program facility (coached training, leagues, rehab/recovery, spa, restaurant/bar) positioned as premium advanced training for serious athletes; two segments — adult competitors, and high-school athletes whose parents pay for coaching as a path to top colleges. Use when a concept plays out differently for a services business.
  - **Franklin's Bagels / Carpenter Hall Marketing (retired from default).** Served the accounting and finance sessions (S04–S06). Carpenter Hall is too generic and commodity to carry marketing or strategy content. Franklin's workbook remains the reference model where it's already embedded.
  - **Awkward-fit sessions:** S12 (investors), S13 (fundraising) and S16 (cap tables) — a craft chocolatier probably shouldn't raise venture money. Either teach that as the lesson ("why Éclat shouldn't take this term sheet") or pose a clearly labeled hypothetical (e.g., Éclat raising to scale corporate gifting). Decide per session at scoping.

## 5. Delivery & infrastructure

- **Repo layout:** decks as `Fitler_MBA_S0N.html` + `Fitler_MBA_S0N.pdf`; teaching artifacts suffixed by name; `index.html` is a session-card page (all of a session's resources grouped: slides, PDF, artifacts, worksheets, video placeholder rows).
- **Student distribution:** decks (HTML + PDF), handouts and prompts are posted to Discourse after the session.
- **PDF workflow:** `html-to-pdf` skill at **1728×1080**, spot-verified by rendering pages back to images. Print-variant rule applies (§3.2). Scott places binaries manually (MCP text tools can't write binary).
- **Fonts in build sandboxes:** Google Fonts CDN is blocked. Pull Cormorant Garamond and Inter from `raw.githubusercontent.com/google/fonts/main/ofl/[font]/`, install to `~/.fonts/`, run `fc-cache -f` before PDF generation.
- **GitHub MCP** (`github:create_or_update_file`): reliable for text files; SHA must be the *current* blob SHA — refetch after any local commit. Files >~1MB return empty content; binary renames happen locally via `git mv`.
- **Filesystem MCP** (`/Users/scottsill/`): reliable, with one critical bug — `$$` in `edit_file` `newText` silently collapses to `$`, breaking JS. Use `write_file` with full content for any block containing `$$`.
- **Local prep path:** `/Users/scottsill/Dropbox/Documents/Clients/Fitler Club/Fitler MBA/presentations`. Prep files (handoffs, scoping docs) stay local; only finished assets go to the repo.
- **Build model:** Fable (Mythos tier) for heavy build chats; Opus fallback; Sonnet fine for scoping/design.
- **Idea Forge:** deployed as claude.ai public share link (v1.2); model fallback chain `claude-opus-4-7 → claude-opus-4-6 → claude-sonnet-4-5 → claude-sonnet-4-20250514`, first success cached per session, fail-fast on non-model errors.

## 6. Session index

| # | Title | Status | Notes |
|---|---|---|---|
| S00 | Program Preview Night | Delivered | Deck + PDF in repo |
| S01 | The Entrepreneurial Mindset | Delivered | Idea Forge v1.2 debut — "star of the show"; Part 1 ran 75 min vs. 45 planned |
| S02 | Problem–Solution Fit / Customer Discovery | Delivered | Value Proposition Canvas artifact |
| S03 | Business Model Innovation | Delivered | BMC artifact; post-mortem produced the 48-hour rule and participation-beat rule |
| S04 | Accounting I — The Language of Business | Delivered | Franklin's Bagels ledger artifact (15-event predict-before-reveal ladder), Carpenter Hall; ran short → elasticity doctrine |
| S05 | Accounting II — Understanding What the Numbers Tell Us | Delivered | Peloton three-chapter case (Darling / Bill / Survivor); 26 slides; toolkit-then-story; ran ~110 min. Session cards shipped on index.html |
| S06 | The Price of Money (Finance / Capital Markets) | Delivered | 36-slide deck + Franklin's DCF workbook; recording posted |
| S07 | *(title to confirm)* | Delivered *(confirm)* | Deck chassis reused for S08. Not the pro forma session — pro forma/WACC moved to a later session. Open cleanup: missing repo assets, unbuilt Experiment Card |
| S08 | Pricing Strategy & Revenue Optimization | Delivered *(confirm)* | 24 slides on the S07 chassis; eleven pricing strategies in three movements; 13 embedded photos. Sales-process content and price clinic moved to overflow → S17. AI block take-home (P4 Competitive Analysis, P5 Pricing Analysis) |
| S09 | Marketing & Go-to-Market Strategy | Delivered 2026-09-15 | 12-slide sparse deck (~40 min) + live Éclat Chocolate workshop with founder Chris Curtin present, no slides; Éclat supplied ~$250 of samples. Room stayed to 8:30. See changelog |
| S10+ | — | Unscoped | Original syllabus is the reference spine, resequenced as needed. Éclat is the default case |

## 7. Continuity tracker (introduced vs. deferred)

**Introduced:** three statements + interconnection (S04); ratios/gauges, burn & runway, source-strip reading (S05); PV/FV, DCF/NPV/IRR, terminal value via P/E & P/Sales, debt vs. equity, leverage/DuPont, beta-as-intuition, options/hedging via CEO collar (S06); eleven pricing strategies (S08); BMC + VPC recap as marketing's foundation, marketing as the story of the change you seek, Godin's "people like us do things like this," market-entry scenarios, buyer-journey stages, brand vs. product marketing, Get/Keep/Grow + LTV vs. CAC, smallest-viable market test (S09).

**Deferred, with owed destinations:**
- Amortization; cash vs. accrual methods (deferred from S04 → future accounting touchpoint)
- Pro forma build + full WACC treatment → session TBD, **must land before S12** (originally S07). Runs on the Éclat-shaped assumptions model (§4)
- Valuation & exits (multiples beyond P/E & P/S, EV/EBITDA, "what's a good multiple") → future-session candidate
- CAPM formula → excluded by design program-wide; beta taught through drivers only
- Sales process (pilots, indirect customers, sales flow) + price clinic → S17 (from S08)
- Crossing the Chasm / whole product (Moore) → S17 (dropped from S09 deck; touched in Scott's commentary)
- Idea Forge Deep Dive → v2.0 (JSON crash on large responses; needs dedicated build)

**Callback discipline:** never say "as we saw in Session X" unless the session index confirms it happened.

## 8. Decision log (append-only)

- **2026-05 (S01):** Idea Forge shipped v1.2 without Deep Dive (deliberate cut after JSON parser fight); claude.ai share link chosen over VPS deployment; Anti-Squirrel protocol established as sequencing rule.
- **2026-06 (S02 era):** "Discourse ≠ Discord" corrected everywhere. Archive system designed: canon + decision log + session index + continuity tracker, maintained as a byproduct of each build chat.
- **2026-07 (S03 post-mortem):** 48-hour deck rule; participation beats every ~10 min; live/reactive > scripted.
- **2026-07 (S04):** Predict-before-reveal established as core mechanic; artifact links released post-session; amortization and cash-vs-accrual deferred; canon v1 drafted (push missed — see provenance note).
- **2026-07 (S05):** Vote-before-reveal rejected for material the room is still learning (participation-suppression rule); toolkit-then-story architecture; source strips + benchmark hygiene became hard rules; index.html rebuilt as session cards; standing AI block promoted to permanent structure; S06 initially scoped as pro forma.
- **2026-08-04 (S06 scoping):** S06/S07 resequenced, six-act architecture locked — see changelog.
- **2026-08-04 (S06 build):** deck + workbook shipped same day as scoping — see changelog.
- **2026-09 (S07–S08, backfilled):** Pro forma/WACC moved off S07 to a session before S12; S08 sales-process content deferred to S17; AI block run as take-home prompts; human-voice slide rule (after two S08 drafts rejected).
- **2026-09-15 (S09):** Astra "eight decisions" canvas framework rejected as the lecture spine; lecture rebuilt as a nine-beat, 12-slide sparse deck; Éclat workshop run freeflow with the founder present.
- **2026-09-28 (S09 post-mortem):** Éclat adopted as the standing program case; Carpenter Hall retired from default; Main Line Sports Institute kept as the fictional services counterpart; AI moves inside the live workshop as the standard format.
- **2026-09-28 (Chris Curtin debrief):** Chris agreed to continue with the class; no detailed financial disclosure. Éclat financial work runs on a labeled assumptions model.

## 9. Deferred backlog (Anti-Squirrel holding pen)

- Idea Forge v2.0 Deep Dive (dedicated build session)
- Obsidian MCP setup
- VPS deployment polish
- Discourse harvesting
- Peloton FY2021 guided reference handout (handoff doc exists; needs dedicated build chat)

## 9a. Open items (owed, not deferred)

- **Two-landing decision** after S09's 8:30 finish (§4).
- **S07/S08 backfill:** confirm S07 title and the S07/S08 delivery rows (§6).
- **S07 cleanup:** missing repo assets, unbuilt Experiment Card.

---

## 10. Changelog

### 2026-09-28 — Chris Curtin debrief: Éclat continues, no detailed financials
- Scott debriefed with Chris after S09. Chris is on board to keep working with the class but does not want detailed financial disclosure. The planned case brief for Chris is no longer needed and is removed from open items.
- Real-company guardrail rewritten (§1): Éclat financial figures are always labeled assumptions, never presented or implied as actuals, never attributed to Chris. Benchmark hygiene (§2.5) cross-referenced.
- New doctrine (§4): Éclat financial sessions — pro forma, unit economics, valuation, cap table — run on an **Éclat-shaped assumptions model** with every input labeled and its build method shown. Teaching angle: building defensible assumptions when real numbers aren't available.
- Continuity tracker: the owed pro forma/WACC session (before S12) uses this model.

### 2026-09-28 — S09 post-mortem: Éclat becomes the standing case; AI moves inside the workshop
- **What worked:** a real company, its founder in the room (Chris Curtin, Éclat Chocolate), product to taste (~$250 of samples supplied by Éclat), and a live whole-room build. Highest energy and engagement of the program to date; the room stayed until ~8:30, an hour past the published end.
- **Case vehicle decision:** Éclat is the default case going forward — real, easy to picture, tasteable, straightforward, with direct-consumer and B2B motions that map onto the cohort's own businesses. Carpenter Hall retired from default use (too generic and commodity outside accounting). Main Line Sports Institute kept as the fictional services counterpart. Real-company guardrail added (§1).
- **Structure decision:** workshops include AI in the analysis and plan development. Room-decides / AI-drafts / room-critiques loop with F/A/Q tagging, one driver, prompts loaded ahead, pre-generated fallback on hand (§4). The standing AI block merges into the workshop.
- **S09 deck history:** the Astra-derived "eight decisions" canvas deck was rejected — it missed marketing's mission (the story of the change you seek, earning interest and trust to drive action) and read as AI language. Rebuilt as a 12-slide sparse deck: BMC + VPC recap → VPC stories about the customer → marketing as the connector → Godin "people like us" → five market-entry scenarios → buyer journey and campaign fit → brand vs. product marketing (Red Bull/Nike vs. Nike shoe/Disney World) → LTV vs. CAC → smallest market test, then expand. Sparse-deck pattern logged (§3.2); human-voice rule promoted to hard rule 14 (§2).
- **Continuity:** Get/Keep/Grow + LTV:CAC delivered (closes the S08 deferral). Moore → S17. Pro forma/WACC still owed before S12.
- **Open:** two-landing decision; S07/S08 backfill confirmation (§9a).

### 2026-08-04 — Canon reconstructed & committed; S06/S07 scoping decisions
- Canon rebuilt from the conversation record and shipped decks after the July draft was never pushed. This is the first committed version. Palette drift between S04 (predecessor tokens) and S05 (locked standard) documented in §3.1.
- **S06 confirmed as "The Price of Money"** (finance/capital-markets literacy); **"Building a Pro Forma" moves to S07.** Rationale: learn the pricing math first, then build the thing that gets priced. *(Superseded 2026-09: pro forma moved again, to a session before S12.)*
- S06 architecture: six acts (Price of Money · Price of Time · Pricing the Future · Two Flavors of Capital · How Risk Gets Priced · The Zoo), ~109 min nominal with named expansion joints and compression valves; elasticity promoted to doctrine (§4).
- Spectrum of Returns anchor visual placed in Act 2A (where rates first matter mechanically), per the within-deck sequencing rule; Act 2B opens with a required DCF definition/anatomy bridge slide.
- Standing AI block merged *into* Act 2B: live DCF assumption-feeding on a fully pre-built model; no separate AI segment this session.
- Case vehicles: Franklin's Bagels (primary DCF), Carpenter Hall Marketing (expansion-joint second scenario). CEO collar chosen over farmer for the Act 5 hedging story.
- New standing artifact class: **Excel workbook** (assumptions → P&L → cash flow → valuation + annotations tab), designed as the S07 pro-forma chassis; independent formula verification required.
- CAPM formula excluded program-wide by design; beta taught through drivers as intuition.
- Multiples treatment bounded to one slide (P/E, P/Sales); full valuation/exits treatment flagged as future-session candidate.

### 2026-08-04 — S06 build shipped: "The Price of Money" deck + Franklin's DCF workbook
- **Deck:** `Fitler_MBA_S06.html`, 36 slides across the six locked acts. Anchor visual (Spectrum of Returns) appears in Act II and returns annotated in Act V to cash the BLUF ("every financing conversation is someone pricing your risk"). Iterated through visual + copy critical review against the finance-naive-room persona.
- **Verified market rates** on the spectrum (benchmark hygiene, hybrid strategy): Fed funds 3.50–3.75% (FOMC target, Jul 2026), 10Y Treasury ~4.7% (close, Aug 3 2026), IG corporates ~5.2% and high yield ~7.0% (ICE BofA index effective yields, Jul 2026). Equities (~10%/yr long-run) and VC (25–30%+ target) stylized and explicitly labeled solid-dot (quoted) vs. hollow-dot (historical/target) on the visual itself.
- **Franklin's Bagels 5-year pro forma (locked):** revenue 780 / 850 / 1,150 / 1,650 / 1,950 ($K); FCF 95 / 115 / **(70)** / 205 / 290 — second location opens Yr 3 (capex $210K + margin dip to 14%), acceleration Yrs 4–5. At r = 20% and 5× Yr-5 FCF exit: NPV **$917K**, terminal share **63.6%** (the "lab coat" kicker holds across 10–30% rates: 60–67%). IRR at a $700K ask: **27.7%**.
- **House leverage case (locked):** $500K house → $700K in 5 yrs. All-cash: $200K profit, 7.0%/yr. Leveraged ($100K down, $400K at 6.00%/30yr, real payments $2,398/mo as negative flows): $83.9K profit, 9.2%/yr. Vote is genuinely contested — dollars vs. rate — which *is* the Act IV lesson. The "$400K question" (idle cash in an index fund at a labeled stylized 10% → combined $328K profit) built as the named expansion-joint slide; the room's own follow-up question deploys it.
- **Marcus's collar (Act VI story):** fictional CEO of an AI-powered SEO company post-NASDAQ IPO; 1M shares at $32 = $32M paper, lockup-bound; puts at $25 funded by calls at $45 → outcome collared $25M–$45M at zero net cost.
- **Workbook:** `Fitler_MBA_S06_Franklins_DCF.xlsx` — Assumptions → P&L → Cash Flow → Valuation → Annotations; live rate/multiple/price levers (yellow); static formula-built 5×5 sensitivity grid (rates 10–30% × exits 3–7×, no Data Table feature); stacked NPV-composition bar chart; XNPV/XIRR note in Annotations. All 89 formulas recalculated clean and verified against independent Python computation (NPV, IRR, TV share, grid spot checks — exact matches).
- **Deck↔workbook reconciliation:** P&L decomposition (EBITDA margins 15/16/14/16/18%, capex, ΔWC) reproduces the deck's FCF line to the dollar.
- **New canon learnings logged:** PDF print-variant rule (§3.2 — step-reveals must be pre-shown before `html-to-pdf`); workbook color code standardized (§3.3); N-key facilitator notes clarified as optional when Scott facilitates (§3.2).
- **Repo state:** deck HTML, PDF, and workbook binaries placed by Scott via local git (single commit with `git pull` first — MCP pushed index.html and this canon ahead of it). Session card added to index.html with slides / PDF / workbook / recording-placeholder rows.
