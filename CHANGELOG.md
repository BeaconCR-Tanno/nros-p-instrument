# NROS-P Changelog

All notable changes to the NROS-P instrument are documented here.
Format: [Version] — Date — Summary

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
