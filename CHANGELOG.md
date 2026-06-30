# NROS-P Changelog

All notable changes to the NROS-P instrument are documented here.
Format: [Version] — Date — Summary

---

## [Unreleased — v1.0-dev] — 2026-06-30

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
