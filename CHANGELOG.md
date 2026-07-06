# NROS-P Changelog

All notable changes to the NROS-P instrument are documented here.
Format: [Version] — Date — Summary

---

## [v1.3.1-dev] — 2026-07-06

### Revised — Opening Screen Professionalization
- Opening screen redesigned toward a black / white / grey clinical presentation with restrained Beacon green highlights.
- Removed the large front-page Beacon man / globe art from the landing screen; landing now opens with typography and a concise clinical positioning statement.
- Replaced colorful red/blue/cyan NROS-P hero styling with black/white/grey text and Beacon green only on the specialty `P` highlight.
- Removed decorative star row from landing/header presentation.
- Subscale chips changed from blue badges to neutral grey clinical chips.
- Development preview notice changed to black/grey with a narrow Beacon green accent bar.

### Revised — Logo Asset
- Embedded Adrian-uploaded Beacon logo as the current correct logo source.
- Optimized uploaded 1254×1254 JPG into `assets/beacon-logo-correct-2026-07-06.webp` for lower file weight.
- Updated hidden HTML logo slots used by header/report; kept logo asset out of JavaScript to preserve parser stability.

### Development Report
- Report written: `TANNO_CORE/documents/NROS_P_v1.3.1_OPENING_SCREEN_BRAND_REVISION.md`
- Patcher: `C:/Users/robbe/AppData/Local/Temp/patch_nrosp_v131_brand_landing.py`
- Syntax: `node --check` clean

---

## [v1.3.0-dev] — 2026-07-06

### Revision Request — Lisa / Kurve (logged 2026-07-06)
**Requester:** Lisa, Business Coordinator at Kurve
**Log file:** `TANNO_CORE/documents/REVISION_REQUEST_LISA_v1.3.0.md`

### Added — Multi-Select Diagnosis
- **Old:** Single dropdown, one diagnosis at a time
- **New:** Checkbox list — select all that apply
- **Options:** Primary Immune Deficiency, Specific Antibody Deficiency, PANS/PANDAS, Mold/MARCoNS/Mycotoxin Infection, Lyme Disease, Vaccine Injured, Regressive Autism, Formal Autism Diagnosis, Confirmed Autism Genetic Profile, Other (with free-text field)
- Formal Autism Diagnosis checkbox still reveals the expanded autism card with Vaccine Injured / Regressive / Genetic Profile / gene chip entry

### Added — Pre/Post-INIG Assessment Structure
- **New screen:** Assessment Type selector after Flare gate
- **PRE-INIG ASSESSMENT** — large bold amber header on all domain screens
- **POST-INIG ASSESSMENT** — large bold teal header on all domain screens

### Added — Post-INIG Screen
New `rInig()` screen inserted before Review, collects:
- INIG start date, weeks/months using, dosing schedule, still using Y/N
- Overall improvement (dropdown)
- Caregiver narrative description of improvements
- Any new symptoms (free-text)
- Domain-by-domain change tracking with pills: **Improved / No change / Worsened / Not applicable / Unknown**
  - Domains: Sleep, Seizures, Communication, Motor, Cognition, Behavior, Immune, Inflammation, GI, Anxiety, OCD, Sensory
- Optional notes per domain

### Infrastructure
- Commit: `f247203` — main branch
- Syntax: `node --check` clean
- Deploy: 200 OK, 451KB, https://nros-p-dev.beaconcr.com

---

## [v1.2.1-dev] — 2026-07-03

### Fixed — Light Theme Color Pass
- **OCD / sensitive section box:** Replaced dark purple background (`#FAF5FF` + purple border + `#C4B5FD` text) with amber/yellow clinical advisory style (`#FFFBEB` + `#F59E0B` border + `#78350F` dark text). Purple was unreadable on the new white background.
- **Crisis box (988 section):** Text color corrected from light pink `#FCA5A5` (dark-theme color) to dark red `#7F1D1D` — high contrast on white.
- **Framing box:** Switched to light blue `#F8FAFF` background with blue border — clearly advisory without feeling alarming.
- **Flag cards in report:** Same red fix — dark red text on light red background.
- **Crisis number (988):** Corrected to dark red `#DC2626`.
- **Modal:** Mission + changelog section updated to light theme colors.

### Process
- **Dev log auto-update:** Dev log modal inside the app now updated with every version bump. The `v2026` chip in the header always reflects the most recent changes.

### Infrastructure
- Commit: `pending` — main branch
- Syntax: `node --check` clean

---


## [v1.1.6-dev] — 2026-07-02

### Added — Dev Log Modal + Feedback Boxes
- **Dev log modal:** Clicking `v1.1.6-dev` chip in header opens a bottom-sheet modal with:
  - BeaconCR mission statement (why PRO instruments matter, PTEC foundation)
  - Full development history (v1.0 → current, changelog entries)
  - Contact CTA: `admin@beaconcr.com` + `beaconcr.com`
  - "Designed in America 🇺🇸" footer inside modal
  - Closes on X button or tap-outside
- **Skip reason text box** (conditional): shown on review page only if caregiver skipped ≥1 question. Asks for optional context (e.g. "too young", "didn't apply"). Autosaves to localStorage, included in session JSON export.
- **Suggestion text box**: shown on every review page. Open-ended — caregivers can suggest questions or give feedback. Feeds directly into session data for clinical team review.
- Both text boxes wired to `buildLog()` → `skipReason` and `suggestion` fields in session JSON.

### Infrastructure
- Commit: `a4ba3a1` — main branch
- Deploy: `https://nros-p-dev.beaconcr.com` — v1.1.6-dev confirmed live
- Syntax: `node --check` clean, 45,402 chars JS

---

## [v1.1.4-dev] — 2026-07-02

### Changed — Header & Branding
- **Hi-res BeaconCR logo:** Replaced prior JPEG with new 1081×1081 hi-res Vitruvian Man / DNA helix / globe mark. Circular crop with cyan glow border. Embedded as base64 in HTML (no external dependency).
- **Header redesign — beaconcr.com consistency:** Sticky header now matches beaconcr.com aesthetic:
  - Background: `rgba(8,12,26,0.98)` with `backdrop-filter: blur(16px)` (deeper navy, stronger blur)
  - Border-bottom: subtle `rgba(0,212,212,0.12)` cyan line (replaces hard `--border`)
  - Fixed height: `60px`
  - Logo: 44px circular with cyan border + box-shadow glow
  - **Brand wordmark** right of logo: "BEACON" in white bold caps + "CLINICAL REGISTRY" in cyan spaced caps (matches beaconcr.com nav logo treatment exactly)
  - **Vertical divider** (1px, 28px tall) separating brand from NROS-P symbol
  - NROS-P symbol at same 18px, stars row preserved
- **Landing hero logo:** Enlarged from 96px → 120px with enhanced glow (`box-shadow: 0 0 32px`)
- **File size reduced:** 530KB → 373KB (new logo JPEG is smaller in base64 than the original)

### Infrastructure
- Commit: `46939df` — main branch
- Deploy: `https://nros-p-dev.beaconcr.com` — 200 OK, 313ms
- Syntax: `node --check` clean, 37,677 chars JS

---

## [v1.1.3-dev] — 2026-07-02

### Added — Review Page
- **Review screen** inserted between Caregiver Wellbeing and Completion
- Shows every question (all 101 PTEC items + 5 burden items) grouped by domain with color-coded answer pills
- **Per-section Edit button** (✏️) jumps back to that domain's page
- **Sticky return-to-review bar** on domain/burden pages when editing from review — cyan bar with "← Back to Review" button
- **Submit Final Assessment** button — the only path to completion from review
- Caregiver Wellbeing has its own ✏️ Edit entry in review
- Session info block at bottom of review (child name, age, diagnosis, flare, session ID)
- `rv` (return-from-review) state flag persisted in localStorage; cleared on new assessment

### Infrastructure
- Commit: `1e06edd` — main branch
- Syntax: `node --check` clean, 37,510 chars JS

---

## [v1.1-dev] — 2026-07-04

### Changed — UX Architecture
- **Domain-per-page layout:** All questions within a domain now appear together on one scrollable page (replaces one-question-per-screen flow). Each domain = one page, 10 domains = 10 pages.
- **Answer tiles — high contrast:** Replaced blending dark cards with colored pill buttons: 0=green, 1=yellow, 2=orange, 3=red. Each pill has distinct background, border, and text color for clear contrast against the dark background.
- **NROS-P symbol redesign:** N=red (#DC2626 with glow), R=white, O=navy (#3C3B6E with glow), S=red, -=slate, P=cyan. Stars row (★★★★★) below symbol in header. Large hero version on landing with text-shadow glow effects.
- **Beacon logo — real image:** Removed placeholder SVG. BeaconCR logo (1280×1280 JPEG) embedded as base64 data URI. Circular crop with cyan border. Appears in: sticky header (36px), landing hero (100px, glowing), and report header (44px).
- **"Designed in America" placement:** Removed from sticky header badge. Now at bottom of landing page and bottom of report (footer line).
- **Answered indicator:** Cyan dot appears on question number after answering. Skipped questions fade to 50% opacity.
- **Progress bar:** Now tracks domain progress (1 of 10) rather than individual questions.

### Added
- Stars & Stripes color treatment throughout NROS symbol
- Gradient progress bar (red → cyan, patriotic)
- Caregiver burden section uses amber color scheme to visually distinguish from child domains
- Report footer: "Designed in America • Beacon Clinical Research • beaconcr.com • NROS-P v1.1-dev"

### Infrastructure
- HTML rebuilt via Python builder script (build_nros_p_v11.py) for maintainability
- File size: 359KB (includes embedded BeaconCR logo)
- Commit: main branch, beacon-nros-p Pages project

---

## [v1.0-dev] — 2026-06-30

### Added
- Initial repository scaffolding
- README.md with instrument description and PTEC attribution
- CHANGELOG.md
- .gitignore
- index.html placeholder (full instrument build in progress)

### Instrument Design
- 101-item PTEC framework (Vyshedskiy et al. 2025) adopted as item source
- 10 subscales: Behavior/Mood, OCD, Anxiety, Food Intake, Tics, Cognitive/Developmental, Sensory, Other, Sleep, Health
- BeaconCR additions defined: flare gate, treatment module, caregiver burden co-scale, CGIC
- Safety flag architecture: 988 prompt on suicidal/homicidal ideation items ≥ moderate
- Registration gateway: caregiver + child info, relationship, consent checkbox
- Scoring model: domain raw averages (0–3 scale), caregiver burden separate, CGIC separate
- Demo mode architecture: localStorage, no backend, synthetic data only

### Infrastructure
- GitHub repo: BeaconCR-Tanno/nros-p-instrument
- Cloudflare Pages project: beacon-nros-p (pending deployment)
- Target subdomain: nros-p-dev.beaconcr.com

---

_Instrument based on PTEC © 2022–2026 Neuroimmune Foundation. Used with attribution per open availability terms._
_NROS-P additions © 2026 Beacon Clinical Research._
