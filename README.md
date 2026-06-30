# NROS-P — NeuroRecovery Outcome Scale: Pediatric

**PANS/PANDAS Caregiver Outcome Instrument**
Beacon Clinical Research | Version 1.0-dev

---

## What Is NROS-P

NROS-P is a caregiver-reported outcome (ObsRO) instrument for tracking symptom burden and treatment response in children with PANS, PANDAS, and related inflammatory brain disorders.

Built on the validated **PTEC framework** (Vyshedskiy et al., *Pediatric Reports*, 2025 — 101 items, 10 subscales, Cronbach's α = 0.96) with BeaconCR enhancements:

- **Flare status gate** — baseline vs. active flare tracking
- **Treatment module** — current intervention logging
- **Caregiver burden co-scale** — burnout assessment
- **Caregiver Global Impression of Change (CGIC)** — follow-up anchor
- **Safety flag system** — 988 Lifeline prompts for high-risk items
- **Admin notification** — Lisa's portal receives submission alerts
- **Longitudinal data architecture** — baseline → 1mo → 3mo → 6mo → 12mo

## Instrument Attribution

PTEC items are reproduced with credit to:
> Vyshedskiy A, Conkey A, DeWeese K, Junghanns FB, Adams JB, Frye RE.
> "Validation of Pediatric Acute-Onset Neuropsychiatric Syndrome (PANS)-Related
> Pediatric Treatment Evaluation Checklist (PTEC)."
> *Pediatric Reports*. 2025;17(4):81. doi: 10.3390/pediatric17040081
> Neuroimmune Foundation — freely available at neuroimmune.org/PTEC

## Subscales (10)

| # | Subscale | Items |
|---|---|---|
| I | Behavior / Mood | 20 |
| II | OCD | 28 |
| III | Anxiety | 5 |
| IV | Food Intake | 8 |
| V | Tics | 2 |
| VI | Cognitive / Developmental | 7 |
| VII | Sensory | 6 |
| VIII | Other (incl. urinary, safety items) | 11 |
| IX | Sleep | 5 |
| X | Health | 9 |

Plus BeaconCR additions: Flare Context, Caregiver Burden (5 items), CGIC (7-point).

## Status

| Channel | URL | Status |
|---|---|---|
| Dev preview | nros-p-dev.beaconcr.com | 🔧 Building |
| Production | nros-p.beaconcr.com | ⏳ Pending |

## Demo vs Production

**Demo mode** (current): synthetic data only, localStorage, no backend.
**Production mode**: requires HIPAA hardening checklist cleared + BAAs signed + Adrian/Tamara sign-off. See `NROS_P_ARCHITECTURE_v0.2.md` for full requirements.

## Repository Structure

```
index.html          — NROS-P instrument (single-file, self-contained)
CHANGELOG.md        — version history
README.md           — this file
releases/           — archived versions
```

## Beacon Clinical Research

Adrian Benavides, Founder & Operations Director
adrian@beaconcr.com | beaconcr.com | nros-demo.beaconcr.com
