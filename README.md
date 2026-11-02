LIVE WEBSITE (planned canonical): https://rkoperator-ledger.com/

Fallback during cutover: https://senjonanaya.github.io/portfolio-nanaya/

Portfolio — static HTML, CSS, and vanilla JavaScript only. No build step, no
runtime dependencies. Case-study pages need no JavaScript at all.

## Page map

- `index.html` — home page (YoRHa shell): hero, proof, selected work,
  how I check my work, about, contact footer. Links `tokens.css` +
  `flex.css`. Canonical `https://rkoperator-ledger.com/`.
- `work/rk.html` — RK Operator Ledger case study with the walkthrough video
  (native controls, `preload="none"`). Canonical
  `https://rkoperator-ledger.com/work/rk.html`.
- `work/pathag.html` — Pathag case study (text-led; the workflow illustration
  appears only as the labelled home-page thumbnail, never as a screenshot). Canonical `https://rkoperator-ledger.com/work/pathag.html`.
- `work/kitacred.html` — KitaCred case study. Canonical
  `https://rkoperator-ledger.com/work/kitacred.html`.
- `tokens.css` — shared palette, type, spacing, and motion tokens. Linked by
  every page; case-study pages must not depend on `flex.css`.
- `work/work.css` — quiet reading layout for case studies: same palette and
  type, plain headings, 68-character measure, no grid background, no
  ornamental borders, no bracket labels, no all-caps body text, no game
  lore. Relative links only (`../tokens.css`, `work.css`,
  `../assets/...`).
- `flex.css` — YoRHa home chrome (shell, profile, proof row, work index,
  responsive rules). Design tokens live in `tokens.css`.
- `assets/Galvin_Gonzales_Resume.pdf` — public CV (phone-free, UP email;
  maintained outside this pass).
- `assets/favicon.svg` — favicon, referenced relatively from every page.
- `assets/og-preview.jpg` — 1200x630 social preview served from the new domain.
- `assets/rk-operator-ledger-poster.jpg` / `-preview.webm` / `-preview.mp4` —
  kept for the RK case study only; the home page shows no video.
- `assets/pathag-workflow.png` — full-file design illustration, used as the
  Pathag home thumbnail (cover-cropped) and labelled as a presentation
  illustration, never as a live UI. Not a verified product screenshot.
- `assets/kitacred-concept-mockup.jpg` — hero crop from the team's Canva
  landing-page render (no personal or financial details; the
  sample-applicant results frame was deliberately excluded). Captioned as
  a concept mockup, never a live service. The Canva share link stays out
  of the repo and the site.

Every page has its own title, meta description, canonical URL, and Open
Graph tags. No page names Steradium.

## Content hierarchy (home)

The first viewport answers five questions without scrolling: who, what they
build, what shipped, what evidence supports it, how to contact.

1. `header#profile` — name; "Third-year BS Computer Science, UPLB";
   "Software, data, and applied AI."; "Philippines · Seeking a January 2027
   internship."; one value sentence (a shorter variant swaps in at 480px
   and below); contact links (email, GitHub, LinkedIn, CV). Portrait is
   112px desktop, 88px tablet, 64px small phones.
2. `section#work` — three primary rows (RK Operator Ledger, Pathag,
   KitaCred). Each row: a 4:3 thumbnail, one plain sentence, role/team, an
   Outcome/Scale evidence pair, and a links line. Thumbnails enlarge on
   hover and keyboard focus; activating one opens the enlarged view in a
   dialog (Escape or backdrop click closes, plain-link fallback without
   JavaScript). Pathag uses the workflow illustration, labelled as a
   presentation illustration, not a live UI. Two short archive rows (CIEL,
   TAP:SCANS) with thumbnails and compact evidence.
3. `section#about` — three sentences: education; fintech, applied-AI, and
   machine-learning interests plus full-stack building; working style.
4. `section#skills` — four groups (Frontend incl. React/JavaScript; Backend
   & Data; Machine Learning; Tools), all resume-evidenced. No full About
   page.
5. `section#proof` — three award points, one line each, near the bottom.
   Each award appears exactly once in the summary; detail may repeat inside
   a case study.
6. Footer `#contact` — contact, CV, GitHub, LinkedIn; the `GLORY TO MANKIND`
   flourish stays on the home page only.

Known first-viewport trade-off: the 112px portrait, larger thumbnails, and
full Outcome/Scale pairs cost vertical space. At 1280x800 the three primary
names and descriptions still fit; at 390x844 the third name may fall below
the fold. Body text was never reduced to compensate.

## Case-study template (work/*.html)

Back link, title, one-line summary, metadata (role, dates, team, stack,
links), context, constraints, what I did, key decisions, verification,
result, limitation (including what the project does not prove), what I
would do next, repository/demo links. Quiet layout, no JavaScript needed.

## Copy rules

- Plain language: one idea per sentence, active voice. No unexplained
  acronyms in top-level copy; technical names live only in a metadata or
  Stack line, or inside a case study.
- Every claim carries a number, role, artifact, award, or link. No
  production use, real users, or client impact: use "prototype", "demo",
  "sample", "coursework" where accurate.
- Banned filler: passionate, innovative, robust, seamless, cutting-edge,
  dynamic, results-driven, detail-oriented, leverage.
- Truthful labels: CIEL matches against a small gallery of enrolled photos
  (not one photo); the KitaCred mockup explains the assessment flow but does
  not prove each score; RK ranks 2,264+ disclosure PDFs (ranked, not all
  fully parsed); year line stays at "Third-year" per the existing page.
- Each case study states what the project does not prove. Next steps are
  prospective engineering notes, not commitments.

## Hosting path

- Source of truth: `SenjoNanaya/portfolio-nanaya`, branch `master`.
- Deploy target: Cloudflare Pages, no build command, output directory `/`.
- Canonical URL: `https://rkoperator-ledger.com/`. `www` redirects to the apex.
- The hosted registry demo (`edge.rkoperator-ledger.com`) is offline, so the
  RK evidence link points at the `pse-dividend-analysis` repository with a
  visible offline note inside the RK case study.
- GitHub Pages stays reachable as a fallback during cutover. All internal
  links are relative so both hosts work.

## Deployment notes

- Do not push from this lane without confirmation; no DNS or deployment changes here.
- Keep the page static: plain HTML, CSS, and vanilla JavaScript only.
- Proof labels: RK is an individual project (code under
  `pse-dividend-analysis`); Pathag is a hackathon prototype with
  verifier-gated reports; KitaCred is a hackathon demo/mockup with sample
  counts; the Tomasulo comparison is labelled coursework.
- Verification claims trace to `pse-dividend-analysis`
  (`scripts/run_fixture_tests.py`, `fixtures/parser/`) and the ECE 585
  Tomasulo coursework audit report.

Credits:

Influenced by [Lev's CodePen](https://codepen.io/levise/pen/vMzEwr) for the grid line implementation and just the overall how of how I'd implement the YorHa aesthetic.

NieR: Automata UI Design by PlatinumGames.
