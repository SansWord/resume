# Resume — Career Context Hub

**Purpose:** This repo is the **central context hub** for career-related work — keeping the resume current, prepping for networking chats, and prepping for interviews. When asking Claude for help on any of these, point at this repo and Claude can pull from the artifact map below.

The principle: **the resume narrative is downstream of the work.** New writing, side-project shipments, and measured AI experiments should flow into resume updates and chat/interview prep — this CLAUDE.md is how Claude finds them.

---

## Files in this repo

| File | What it is |
|------|------------|
| [`index.html`](index.html) | Live resume page (deployed at https://sansword.github.io/resume/). Source of truth for the public-facing resume. |
| [`print.html`](print.html) | Print/PDF-optimized version of the resume. |
| [`cv.md`](cv.md) | Markdown version of resume content — easier to diff and edit than HTML. |
| [`2026_wen_kai_huang_resume.pdf`](2026_wen_kai_huang_resume.pdf) | Distributable PDF (linked from `index.html` Download button). |
| [`chat_opening_questions.md`](chat_opening_questions.md) | Active prep doc for career conversations (currently scoped to a 30-min Recce founder chat). Templated structure: framing → opening questions → live/follow-up artifacts → expectations → post-chat actions. |
| [`todo.md`](todo.md) | Running list of open resume/portfolio items with context (tabled edits, pending decisions, push status). Check here first when resuming work. |

---

## Publication targets — the 3 major places I publish

Three venues carry my public work. Work flows: project repos → these venues → the resume narrative. **Publishing convention:** prepare + commit locally per repo, then STOP — no `git push` / deploy without explicit go-ahead (publishing is outward-facing and hard to reverse). For drafts that name a third party, get consent first.

### 1. This repo — resume / portfolio
- **Three artifacts that must ALL stay in sync — any content change lands in all three:**
  1. `index.html` — the live page (https://sansword.github.io/resume/), single-column, green accent, project *cards* with dimmed inline descriptors.
  2. `cv.md` — markdown mirror; also linked from the page as the "Resume in Markdown" (LLM-friendly) download. Mirrors `index.html` order + descriptors.
  3. `print.html` → `2026_wen_kai_huang_resume.pdf` — the downloadable PDF (linked from the page's Download button).
- Deployed via GitHub Pages from this repo.

**Resume PDF — generation mechanism (keep it in sync as the portfolio's downloadable):**
- `print.html` is the print-optimized **source**; never hand-edit the `.pdf`. After any content change, regenerate:
  ```sh
  cd <repo> && "/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
    --headless --disable-gpu --no-pdf-header-footer \
    --print-to-pdf="2026_wen_kai_huang_resume.pdf" \
    "file://$(pwd)/print.html"
  ```
- **Must be exactly ONE page.** Verify: `mdls -name kMDItemNumberOfPages 2026_wen_kai_huang_resume.pdf` → expect `1`. If `2`: tighten copy and reduce `.project-item` / `.section` spacing (and `.project-desc` line-height) before touching `@page` margins.

**Resume PDF — style preferences (its own condensed design, intentionally NOT identical to the web page):**
- US-Letter, **two-column grid** — left: Summary, Experience, Patent, Education; right: Skills, Projects.
- Body Helvetica ~8.8pt; headings/name Georgia serif; **blue accent `#1a5fa8`** (the web page uses green — deliberate divergence). Header contact line (email, LinkedIn, portfolio URL) is **clickable** — no QR code (the PDF is reviewed on-screen, where links beat a QR). A dedicated "Writing & Notes" callout (sans_blog) sits above the projects so the blog isn't buried.
- Dense and recruiter-skimmable. The PDF is **content-synced, not 1:1**: experience bullets are condensed, projects are tightened one-liners, no card styling/colors. Keep the *claims/numbers/order* aligned with `index.html`/`cv.md`; the shorter phrasing is by design.
- This print/PDF style is the design-parity reference for cover letters — see `cover_letter_pdf_workflow.md`.

### 2. sans_blog — long-form essays & guides
- **Path:** `~/Source/github/sansword.github.io/sans_blog/`
- **Git:** the git root is the *parent* `~/Source/github/sansword.github.io/` (one repo; `sans_blog/` is a subdir). Remote `git@github.com:SansWord/sansword.github.io.git`, branch `main`. **GitHub Pages deploys from `main` on push — push = publish.** Live: https://sansword.github.io/sans_blog/.
- **Structure (hand-built HTML, no static-site generator):**
  - `index.html` = **Writing index** (blog home / article list, newest-first, each with a date). Add a card here when publishing a new post.
  - `doc-tree/index.html` = "The Document Tree" essay (2026-06-24).
  - `tiny-ai-bootcamp/index.html` = "My Tiny AI Bootcamp" essay (2026-04-06).
  - `sd_mock/` = "Leaderboard System Design" study guide (multi-page; shared `assets/style.css`). **Canonical** leaderboard guide — `leaderboard-guide/` is an untracked near-duplicate, ignore it.
  - `landing.html` = untracked portfolio-ish experiment, not part of the canonical flow.
- **To add a post:** create `<slug>/index.html` reusing an existing essay's inline `<style>` template (Source Serif 4 / DM Sans, dark-mode toggle, `.resume-link` in header), then add a dated card to the Writing index (newest on top). Every page carries a prominent **Resume** link in the header (accent+bold on main pages; bordered pill in the sd_mock nav).

### 3. sans_learning — measured notes / learning-in-public
- **Path:** `~/Source/github/sans_learning/`
- **Git:** own repo, remote `https://github.com/SansWord/sans_learning.git`, branch `main`.
- **Structure (markdown):** domain folders `ai/`, `ad-tech/`, `system-design/`; `_templates/topic-template.md` is the note format; `README.md` is the **Notes Index** — update it whenever you add a note. Each note links back to the index at the bottom. Carries a standing disclaimer that notes originate from Claude.ai and may contain inaccuracies.

---

## External artifact map

These sibling repos under `~/Source/github/` hold the substantive work that backs the resume narrative. Reference them when updating positioning, generating talking points, or prepping interview answers.

### Public-facing writing (the narrative layer)

| Path | Description |
|------|-------------|
| `~/Source/github/sansword.github.io/sans_blog/` | Public blog — see **Publication targets §2** above for full structure. Root `index.html` is the Writing index; essays live in subdirs: `doc-tree/` ("The Document Tree"), `tiny-ai-bootcamp/` ("My Tiny AI Bootcamp"). |
| `~/Source/github/sansword.github.io/sans_blog/sd_mock/` | **Leaderboard System Design** study guide (canonical) — full worked design (Redis sorted sets, fan-out, sharding) + companion note on using AI for system design prep. |

### AI / Claude Code work (the credibility layer for the AI pivot)

| Path | Description |
|------|-------------|
| `~/Source/github/sans_learning/` | Measured notes on Claude Code workflows. Contains the **harness-engineering definition** and the **7.8× Sonnet vs Opus cost delta** comparison. |
| `~/Source/github/sans_learning/ai/harness-engineering.md` | Definitional note on harness engineering — use when explaining the term. |
| `~/Source/github/sans_learning/ai/claude-code-model-comparison/comparison.md` | The 7.8× cost delta single-feature study — punchy headline artifact. |
| `~/Source/github/sans_learning/ai/claude-code-feature-cost-analysis/opus-4-7-cost-analysis.md` | Per-story-point cost analysis on Opus 4.7. |

### Side projects (the "shipping things" layer)

| Path | Description |
|------|-------------|
| `~/Source/github/guasi-tw/app/` ⭐ **LATEST & FLAGSHIP (Jun 2026)** | **guasi (我是)** — a *deployed, multi-user* identity-verification product (live at https://guasi.tw). Cross-link the social accounts you own so a banned account's survivors can vouch for a new one; anyone can publicly verify which accounts are the same person. Platform-independent (no API access — relies on publicly auditable posted content). Full production stack: Next.js 16 / React 19, Postgres (Neon) + Prisma, NextAuth, Vercel with per-PR preview deploys on isolated Neon branches, post-deploy smoke tests. Built with agentic Claude Code workflows — maintained `docs/` doc-tree, cost ledger (`docs/operating-costs.md`), devlog. **The strongest "ships real production product end-to-end" artifact.** Unpublished article drafts live in `app/articles/` (see below). |
| `~/Source/github/guasi-tw/app/articles/` 🔒 **DRAFTS (not yet public)** | Six article drafts. Publishable essays: `agentic-context-doc-tree.md` (doc-tree technique for agentic coding — strongest, on-narrative for harness engineering/backend), `guasi-build-retro-blog.md` (six-day solo build retro). Reference/primer: `did-and-vc-primer.md` (DIDs & Verifiable Credentials). Long-form source: `guasi-build-retrospective.md`. **Third-party-sensitive (hold / get consent):** `ansible-vs-guasi-comparison.md`, `ansible-guasi-collaboration-notes.md` (name another real builder). |
| `~/Source/github/sans_ai_mock/` ⭐ **(Apr 2026)** | **AI-round mock interview kit** — Claude Code skill that mode-routes between *interviewer* (`INTERVIEWER.md`) and *developer* via root `CLAUDE.md`. Includes `feedback_rubric.md`, real-run example with feedback, and measured per-mock API cost (~$19–$26). Demonstrates harness engineering (multi-mode agents, security-conscious `CLAUDE.md` audit recipe) on a meta-relevant problem (assessing AI-pair-programming skill). On-narrative for both AI-fluency and harness-engineering claims. |
| `~/Source/github/sans_cube/` | **sans_cube** — real-time smart-cube solve analyzer. BLE ingestion, live 3D rendering, phase detection (CFOP/Roux), Firestore sync. Greenfield code stress-test for AI-assisted workflows. Live at https://sansword.github.io/sans_cube/. |
| `~/Source/github/sans_cube/articles/` | **Living N=5 cost-analysis docs** — per-feature dollar/token/time data, model strategy recommendations. Most senior-engineering rigor on the resume. Key file: `cost-comparison-model-strategy.md`. |
| `~/Source/github/sans_yt_summary/` | Claude skill plugin (YouTube transcript summarizer) with **prompt-injection hardening**. |
| `~/Source/github/cut_sh/` | ffmpeg scripting experiment. Smaller-scope side experiment. |
| `~/Source/github/sans_tiny_ai_bootcamp/` | Bootcamp companion repo (cross-reference with the blog essay if extending). |
| `~/Source/github/sans_claude/` | Claude experiments archive. Lower-priority artifact. |

### Interview prep (the practice layer)

| Path | Description |
|------|-------------|
| `~/Source/github/sans_interview_coding/` | Coding interview prep — `PLAN.md`, `solutions/`, `refresh_knowledge.md`, `improvement.md`. Use when prepping technical screens / coding rounds. |
| `~/Source/github/sans_ai_mock/` | (Also listed above as side project.) Run mock AI-pair-programming rounds against yourself with `start mock interview`. Self-assess via `feedback_rubric.md`. |

---

## How to use this hub

### Updating the resume
1. Read `index.html` (and `cv.md` if doing structural edits) to see current state.
2. Pull recent work from the external artifact map — particularly new entries in `sans_cube/articles/` and `sans_learning/ai/`.
3. Decide what's signal vs. noise: not every artifact deserves a resume slot. Surface only items that strengthen a *specific* narrative claim (cost discipline, harness engineering, shipping greenfield, etc.).
4. Edit `index.html` *and* `cv.md` together to keep them in sync.

### Prepping for a networking chat
1. Identify the company / person; note their domain and any prior shared history.
2. Check artifact alignment: which side projects, writings, or measurements directly map to their problem space?
3. Draft a chat-prep doc in this repo (pattern from `chat_opening_questions.md`): framing → 2–3 opening questions → live vs. follow-up artifacts → expectations → post-chat actions.
4. Live = artifacts shown during the chat (10–30 sec each). Follow-up = artifacts sent within 24h. Don't conflate.

### Prepping for an interview
1. Use `sans_interview_coding/` for technical drilling (data structures, algorithms, system design refresh).
2. Use `sans_ai_mock/` for behavioral / system-design mock runs with self-feedback rubric.
3. Map likely interview signals to existing artifacts (e.g., "tell me about a time you cut cost" → 70% BigQuery cut + N=5 cost analysis).
4. If a gap surfaces during prep that no artifact addresses, that's a signal to *write the artifact* — not to rehearse a hand-wavy answer.

### Narrative coherence check
Before any major chat or application, re-read the resume hero/summary and ask:
- Does the **AI/data-infra convergence** read as one focused direction, or as two parallel tracks (hedging)?
- Does the side-project story make the through-line explicit?
- If a hiring manager skims for 10 seconds, what's the single sentence they walk away with?

If any answer is fuzzy, the narrative needs a pass before the meeting — not after.

---

## Conventions

- This CLAUDE.md is the **index of artifacts**, not the artifacts themselves. Keep entries one-line and link to the file.
- When a new substantive artifact ships in a sibling repo, add it here. When an artifact becomes stale or off-narrative, remove it.
- Chat/interview prep docs (like `chat_opening_questions.md`) live in this repo; raw work products live in their respective project repos.
