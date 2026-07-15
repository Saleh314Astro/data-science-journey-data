# saudi_vs_world — "We Checked / تحقّقنا"

**Question:** Is Saudi Arabia warming faster than the world?

## Files
- `saudi_annual.csv` (date, value) — Berkeley Earth Saudi Arabia **land** temperature anomaly, annual mean, °C. 1881–2020.
- `world_annual.csv` (date, value) — NASA GISTEMP global **land-ocean** temperature anomaly, annual mean, °C. 1880–2025.

## Sources
- Saudi: Berkeley Earth country data <https://berkeleyearth.org/data/> (saudi-arabia-TAVG-Trend.txt). Retrieved 2026-07-14. License: Berkeley Earth, free for research/education.
- World: NASA GISS GISTEMP v4 <https://data.giss.nasa.gov/gistemp/> (annual mean of our monthly file). Retrieved 2026-07-11. Public domain.

## Baseline — read this (don't hide it)
Both series are anomalies relative to the **same 1951–1980 baseline**, so they are directly comparable.
The honest difference is *what* is measured: Saudi is **land surface only**; world is **land + ocean, global**.
Land warms faster than ocean, so expect Saudi > world partly for that reason too.

## Cleaning steps
- Saudi: skip `%` comment lines; take the monthly Anomaly column; group by year, mean (≥6 months present).
- World: annual mean of `gistemp_monthly.csv`, full years only (12 months).

## Load
```python
import pandas as pd
base = "https://raw.githubusercontent.com/Saleh314Astro/data-science-journey-data/main/projects/saudi_vs_world/"
saudi = pd.read_csv(base + "saudi_annual.csv", parse_dates=["date"])
world = pd.read_csv(base + "world_annual.csv", parse_dates=["date"])
```

## Suggested figures
1. Both rolling means (or annual series) on one axis — Saudi vs world.
2. Rate bar: °C/decade since 1980 for each (Saudi ≈ 0.47, world ≈ 0.21).
3. The report-claim check: the ratio (~2.3×) with a one-line verdict.
