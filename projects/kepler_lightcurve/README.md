# kepler_lightcurve — "The Planet Hunter / صائد الكواكب"

**Question:** A star's brightness dips a little, over and over. Is a planet passing in front of it?

## File
- `clean.csv` (time_days, flux_normalized) — detrended, normalized brightness of one star. 2093 points over ~44 days.

## Source
NASA Kepler mission, target **HAT-P-7 (KIC 10666592)**, long-cadence, quarters 1–2, via MAST using `lightkurve`.
Retrieved 2026-07-14. Public domain (NASA).

## Cleaning steps
Stitch two quarters → remove NaNs → remove 5σ outliers → flatten (remove slow stellar trends,
Savitzky–Golay window 401) → normalize to 1.0 → clip to 0.9–1.1.

## TEACHER ANSWER KEY (do not give to students)
- Planet: **HAT-P-7b**. Orbital **period ≈ 2.2047 days**. Transit **depth ≈ 0.7%** (min flux ≈ 0.993).
- Students should find the repeating dip by eye, estimate the period from dip-to-dip spacing, then phase-fold (stretch).

## Load
```python
import pandas as pd
lc = pd.read_csv("https://raw.githubusercontent.com/Saleh314Astro/data-science-journey-data/main/projects/kepler_lightcurve/clean.csv")
```

## Suggested figures
1. Full brightness series (spot the repeating dips).
2. Zoom on one transit (the U-shaped dip).
3. Phase-folded curve at the found period (stretch goal).
