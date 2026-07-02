# NROS-P Changelog

All notable changes to the NROS-P instrument are documented here.
Format: [Version] — Date — Summary

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
