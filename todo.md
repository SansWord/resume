# Resume — TODO

Running list of open items for the resume/portfolio. Newest context first.

---

## Tabled — resume polish (from the 3-reviewer review, 2026-06-24)

### [ ] Tighten the soft-verb Yahoo bullets (needs my input on actual ownership)
**Why:** A hiring-manager review flagged that two of the biggest-sounding Yahoo bullets use hedge verbs that make sharp readers *discount* them. The strongest bullets use ownership verbs (BigQuery 70% cut, Pigeon/MTBF 26×, on-call 1000→0); these two don't:
- *"**Contributed to** Yahoo's hybrid cloud data infrastructure, **supporting** a zero-downtime AWS migration…"*
- *"…**integrating** ranking models into production"*

**What's needed before editing:** my real scope on each — what was specifically mine (designed / led / built) vs. team context. Did I *own* the AWS migration's design or one component? Did I *build* the ranking-model integration or coordinate it? Rewrite to ownership verbs **without overclaiming** — do not inflate blindly.
**Files:** `index.html` (Professional Experience section) + `cv.md` (keep in sync).

### [x] Decide the ★ on the projects section heading — DONE (2026-06-24)
Dropped the ★ glyph, kept the accent-green + bold styling. Heading is now `AI Engineering in Public — Shipped Projects & Measured Writing`.

---

## Other open items

### [x] Sync the PDF (and print.html) — DONE (2026-06-24)
Updated `print.html` to match the current page: hero title → "AI-Assisted Engineering", new tagline, "building and measuring" summary, cut the Writing skills row, and rebuilt Projects (The Document Tree, sans_blog, guasi, sans_ai_mock, sans_cube, + "More work"). Regenerated `2026_wen_kai_huang_resume.pdf` via headless Chrome; trimmed spacing to keep it **1 page** (verified with `mdls`). Generation mechanism + style preferences are now documented in `CLAUDE.md` (Publication targets §1). Experience bullets left as-is (soft-verb fix still deferred below).

### [ ] Push the resume repo
All this session's resume edits are **local / unpushed**: hero quote rewrite, header title → "AI-Assisted Engineering", "currently exploring" → "building and measuring", guasi card (engineering-first + anti-impersonation reframe + smoke-test wording fix), cut "Writing & Learning" skills row, new "The Document Tree" project card, bootcamp link → `/tiny-ai-bootcamp/`, and the `CLAUDE.md` "Publication targets" section. Review, then `git push` (deploys to https://sansword.github.io/resume/).
**Note:** the blog repo (`sansword.github.io`) was already pushed 2026-06-24, so blog links are live; the resume's doc-tree card goes live only on the resume push.

### [ ] (Optional) Enrich the "AI Coding Practice" skills row with concrete keywords
Recruiter suggested backing the AI claims with ATS-searchable terms the projects genuinely contain: LLM APIs, evals / feedback rubric, prompt-injection hardening, token/cost measurement, agent/skill tooling. `index.html` + `cv.md` skills table.

### [ ] Decide on `sans_blog/landing.html` (untracked, never published)
Alternate landing page that duplicates the resume/portfolio. Leaning: leave or delete; do not wire it up (Writing index is the blog home; resume is the portfolio).

### [ ] Decide on `sans_blog/sd_mock/CLAUDE.md` (untracked)
Context/spec doc for the sd_mock mini-site. Commit it to preserve for future sessions, or leave local.

### [ ] Unpublished article drafts in `~/Source/github/guasi-tw/app/articles/`
Publishing was skipped this session. Candidates if revisited: `did-and-vc-primer.md` → sans_learning; `guasi-build-retro-blog.md` → sans_blog. Third-party-naming drafts (`ansible-vs-guasi-comparison.md`, `ansible-guasi-collaboration-notes.md`) need consent before publishing.
