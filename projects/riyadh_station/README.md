# riyadh_station — "Our City's Sky / سماء مدينتنا"

**Question:** Riyadh's own weather record — is home changing?

## File
- `clean.csv` (date, tmax_c, tmin_c) — monthly mean daily maximum and minimum temperature, °C.

## Source
NOAA GHCN-Daily, station **SA000040438 (RIYADH OBS., GSN)** <https://www.ncei.noaa.gov/data/global-historical-climatology-network-daily/>.
Retrieved 2026-07-14. Public domain (NOAA).

## Coverage / caveat
1973-10 → **2011-06** (379 months). This GSN daily record ends in 2011 — enough for a multi-decade
trend, but not up to the present. State this honestly in any claim.

## Cleaning steps
Daily TMAX/TMIN are in **tenths of °C** → divide by 10. Group by month; a month is kept only if it has
**≥20 valid days** for both TMAX and TMIN.

## Load
```python
import pandas as pd
riy = pd.read_csv("https://raw.githubusercontent.com/Saleh314Astro/data-science-journey-data/main/projects/riyadh_station/clean.csv", parse_dates=["date"])
```

## Suggested figures
1. Seasonal climatology (mean TMAX/TMIN by month).
2. Summer-mean (Jun–Aug) TMAX trend across the years.
3. Yearly mean TMAX trend, with a rolling mean.
