# Fitler MBA — Program Canon

*The living design standard for the Fitler MBA program. Every session build consults this document; every cross-session decision lands in the changelog. If a rule here and a habit in a build chat disagree, the canon wins — or the canon gets amended, with a changelog entry.*

**Repo:** `scotts917/fitler-mba` · served via raw CDN (`raw.githubusercontent.com/scotts917/fitler-mba/main/`). GitHub Pages is sandbox-blocked in build chats; the raw CDN is allow-listed.

> **Provenance note (2026-08-04):** Canon v1 was drafted during S04 prep (July 2026) but never pushed to the repo. This is a reconstruction from the conversation record and the shipped S04/S05 decks, current through the S06 scoping decisions. First committed version.

---

## 1. Program identity

- **What it is:** a 20-session, AI-accelerated entrepreneurship program for Fitler Club members, meeting biweekly on Tuesday evenings (60–90 min; demonstrated envelope 90–115). YC-meets-Wharton voice: practitioner-driven, framework-rigorous, zero academic throat-clearing.
- **The cohort:** ~32 mid-career operators and founders (roughly a third active founders/owners). Sharp practitioners **new to structured entrepreneurship frameworks** — not framework-ignorant, not Wharton-fluent. Calibrate everything to that band.
- **Primary failure mode to design against:** confirmation-seeking and solution-first thinking.
- **Facilitator:** Scott Sill — program designer, builder, facilitator. Performs best in **reactive/live mode**, not scripted lecture.
- **Live-example guardrail:** Torev Motors (Scott's board company) may be used only with **public positioning** — no non-public information, ever. Standing rule against public strategic analysis of Torev; AI-block demos use program companies or the session case instead.
- **Community platform:** self-hosted **Discourse** (threaded forum) at `community.fitlermba.com` — *not Discord; these are fundamentally different products*. Postmark for transactional email (`community@fitlermba.com`).

## 2. Hard rules (non-negotiable)

1. **48-hour final-deck rule.** The lecture deck is complete at least 48 hours before the session — for narrative/flow polish and so Scott teaches rested. (S03 post-mortem.)
2. **Participation beat every ~10 minutes** in teach sections — never clustered post-break. Live/reactive consistently outperforms scripted. Satisfy it *structurally* where possible (S04's predict-before-reveal makes every event a beat). (S03 post-mortem.)
3. **Structure before building.** Architecture is discussed and batch-locked before any code or slide work begins. Ask-before-build is the default posture.
4. **Session isolation + shared canon.** Each session's build lives in its own dedicated chat, bootstrapped by pasting this canon plus the session's handoff doc. Anything that outlives the session lands here, with a changelog entry.
5. **Benchmark hygiene.** No unverified industry figures on slides. If a number can't be sourced, it's framed as an explicit assumption to stress-test, not a market fact. ("Verified drag beats borrowed benchmark" — S05.)
6. **Source strips on every computation slide.** The exact statement lines feeding a ratio sit beside the math. The room never holds a balance sheet in memory. (S05.)
7. **Within-deck sequencing rule.** A slide may not reference material the deck hasn't yet introduced.
8. **No quiz dynamics that suppress participation.** Predict-before-reveal is doctrine; vote-before-reveal on material the room is still learning to read is not (S05 v1 "Red Light, Green Light" rejected). Quizzing invites conversation; grading kills it.
9. **Artifact access policy.** Students get artifact links *after* the session (on the homework slide), not during — predict-before-reveal requires one shared board.
10. **Cold-runnable outputs.** Decks, facilitator notes, and artifacts must be operable by a different facilitator with no verbal scaffolding.
11. **Post-mortem discipline.** After each session: capture delivery learnings, log durable decisions here.
12. **Anti-Squirrel protocol.** No chasing useful-but-non-urgent tooling while focused build work is in progress.
13. **Self-rating.** Outputs rated against a 9.5/10 bar with shortfalls named proactively — never polished over.

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
- **Navigation:** keyboard (arrows/space) + touch; fullscreen support; per-slide facilitator notes on the **N key**.
- **BLUF structure:** the session opens with the payoff stated (McKinsey bottom-line-up-front), cashed out later in the deck.
- **Framework slides:** worked examples live *inside* the framework canvas cells — never in a detached strip below.
- **Slides are connective tissue** when a live artifact carries the teach; the deck frames transitions, it doesn't compete.

### 3.3 Interactive teaching artifacts

- **Single-file HTML + vanilla JS** (tiny reactive core at most). CDN-hostable from the repo.
- **State discipline:** pure `compute(events, cursor)` core; rendering is a pure function of derived state; undo = decrement cursor + recompute.
- **No `localStorage`/`sessionStorage`** (unsupported in the claude.ai artifact sandbox). In-memory state; explicit export when persistence matters.
- **Workbooks (S06+):** Excel joins the standing artifact classes. Structure: assumptions tab → P&L → cash flow → valuation (+ annotations tab documenting formulas). Nothing hard-coded downstream of assumptions. Formulas verified independently (recompute in Python, compare).

## 4. Facilitation doctrine

- **Facilitate mode:** the artifact is the answer key, not the lecture. Quiz the room before revealing.
- **Predict-before-reveal** applies to computations *and* concepts (e.g., moving "$10K today vs. $11K next year" until the room splits teaches a discount rate before naming it).
- **Elastic session design (S04/S06 lesson):** every deck ships with named **expansion joints** (stories/scenarios that absorb a quiet room) and **compression valves** (segments that collapse without pedagogical cost). Fixed-length decks caused S04's short landing; elasticity is the insurance.
- **Standing AI block:** 15–20 min per session, demoing on program companies or the session case (never Torev). May be merged into a teaching segment when the segment *is* an AI-driven build (S06 Act 2B).
- **Case vehicles:** Franklin's Bagels and Carpenter Hall Marketing are the recurring fictional program companies (introduced S04). Mundane on purpose — the room sanity-checks assumptions from lived experience.

## 5. Delivery & infrastructure

- **Repo layout:** decks as `Fitler_MBA_S0N.html` + `Fitler_MBA_S0N.pdf`; teaching artifacts suffixed by name; `index.html` is a session-card page (all of a session's resources grouped: slides, PDF, artifacts, worksheets, video placeholder rows).
- **PDF workflow:** `html-to-pdf` skill at **1728×1080**, spot-verified by rendering pages back to images. Scott places binaries manually (MCP text tools can't write binary).
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
| S06 | The Price of Money (Finance / Capital Markets) | Scoped 2026-08-04 | Six-act architecture; Excel DCF workbook; see handoff doc + changelog |
| S07 | Building a Pro Forma | Queued | Inherits the S06 workbook chassis; full WACC treatment lands here |
| S08+ | — | Unscoped | Original syllabus is the reference spine, resequenced as needed |

## 7. Continuity tracker (introduced vs. deferred)

**Introduced:** three statements + interconnection (S04); ratios/gauges, burn & runway, source-strip reading (S05); PV/FV, DCF/NPV/IRR, terminal value via P/E & P/Sales, debt vs. equity, leverage/DuPont, beta-as-intuition, options/hedging via CEO collar (S06, pending delivery).

**Deferred, with owed destinations:**
- Amortization; cash vs. accrual methods (deferred from S04 → future accounting touchpoint)
- Full WACC treatment → S07
- Cash-flow projection depth / pro forma build → S07
- Valuation & exits (multiples beyond P/E & P/S, EV/EBITDA, "what's a good multiple") → future-session candidate
- CAPM formula → excluded by design program-wide; beta taught through drivers only
- Idea Forge Deep Dive → v2.0 (JSON crash on large responses; needs dedicated build)

**Callback discipline:** never say "as we saw in Session X" unless the session index confirms it happened.

## 8. Decision log (append-only)

- **2026-05 (S01):** Idea Forge shipped v1.2 without Deep Dive (deliberate cut after JSON parser fight); claude.ai share link chosen over VPS deployment; Anti-Squirrel protocol established as sequencing rule.
- **2026-06 (S02 era):** "Discourse ≠ Discord" corrected everywhere. Archive system designed: canon + decision log + session index + continuity tracker, maintained as a byproduct of each build chat.
- **2026-07 (S03 post-mortem):** 48-hour deck rule; participation beats every ~10 min; live/reactive > scripted.
- **2026-07 (S04):** Predict-before-reveal established as core mechanic; artifact links released post-session; amortization and cash-vs-accrual deferred; canon v1 drafted (push missed — see provenance note).
- **2026-07 (S05):** Vote-before-reveal rejected for material the room is still learning (participation-suppression rule); toolkit-then-story architecture; source strips + benchmark hygiene became hard rules; index.html rebuilt as session cards; standing AI block promoted to permanent structure; S06 initially scoped as pro forma.
- **2026-08-04 (S06 scoping):** see changelog entry below — S06/S07 resequenced, six-act architecture locked.

## 9. Deferred backlog (Anti-Squirrel holding pen)

- Idea Forge v2.0 Deep Dive (dedicated build session)
- Obsidian MCP setup
- VPS deployment polish
- Discourse harvesting
- Peloton FY2021 guided reference handout (handoff doc exists; needs dedicated build chat)

---

## 10. Changelog

### 2026-08-04 — Canon reconstructed & committed; S06/S07 scoping decisions
- Canon rebuilt from the conversation record and shipped decks after the July draft was never pushed. This is the first committed version. Palette drift between S04 (predecessor tokens) and S05 (locked standard) documented in §3.1.
- **S06 confirmed as "The Price of Money"** (finance/capital-markets literacy); **"Building a Pro Forma" moves to S07.** Rationale: learn the pricing math first, then build the thing that gets priced.
- S06 architecture: six acts (Price of Money · Price of Time · Pricing the Future · Two Flavors of Capital · How Risk Gets Priced · The Zoo), ~109 min nominal with named expansion joints and compression valves; elasticity promoted to doctrine (§4).
- Spectrum of Returns anchor visual placed in Act 2A (where rates first matter mechanically), per the within-deck sequencing rule; Act 2B opens with a required DCF definition/anatomy bridge slide.
- Standing AI block merged *into* Act 2B: live DCF assumption-feeding on a fully pre-built model; no separate AI segment this session.
- Case vehicles: Franklin's Bagels (primary DCF), Carpenter Hall Marketing (expansion-joint second scenario). CEO collar chosen over farmer for the Act 5 hedging story.
- New standing artifact class: **Excel workbook** (assumptions → P&L → cash flow → valuation + annotations tab), designed as the S07 pro-forma chassis; independent formula verification required.
- CAPM formula excluded program-wide by design; beta taught through drivers as intuition.
- Multiples treatment bounded to one slide (P/E, P/Sales); full valuation/exits treatment flagged as future-session candidate.
