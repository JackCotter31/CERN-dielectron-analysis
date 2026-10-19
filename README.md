# CERN Dielectron Collision Analysis

Exploratory analysis of ~100,000 simulated electron–positron collision events
from the public [CERN dielectron dataset](https://www.kaggle.com/datasets/fedesoriano/cern-electron-collision-data)
on Kaggle.

## What this project does

- Loads the raw dataset (via `kagglehub`, so no manual download is needed).
- Explores per-electron kinematics (four-momentum, η, φ, charge) with
  correlation matrices, KDEs and pairwise plots.
- Engineers physics-motivated event features: total energy and momentum,
  transverse momentum, opening angle, ΔR, rapidity, energy/pT asymmetry and
  acoplanarity.
- Reproduces the known resonances in the invariant-mass spectrum —
  **J/ψ ≈ 3.096 GeV** and **Z ≈ 91.19 GeV**.
- Applies an **Isolation Forest** (scikit-learn) as an unsupervised baseline
  anomaly detector; the flagged events concentrate at the extremes of the
  kinematic distribution and in the heavy tail of the mass spectrum.

## Dataset

- 100,000 rows (events) × 19 columns.
- Columns: `Run, Event, E1, px1, py1, pz1, pt1, eta1, phi1, Q1, E2, px2,
  py2, pz2, pt2, eta2, phi2, Q2, M`.
- `M` is the invariant mass of the electron–positron pair.

## Getting started

```bash
git clone https://github.com/<you>/cern-dielectron-analysis
cd cern-dielectron-analysis
pip install -r requirements.txt
jupyter notebook notebooks/cern_collision_analysis.ipynb
