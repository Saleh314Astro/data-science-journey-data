# sunspots — "The Sun's Heartbeat / نبض الشمس"

**Question:** Find the Sun's 11-year pulse — then test whether it explains the warming.

## Files
- `clean.csv` (date, sunspots) — SILSO monthly mean total sunspot number. 1749–2026.
- `sunspots_recent.csv` (date, sunspots) — trimmed to 1880+ for direct merge with temperature.

## Source
SILSO, Royal Observatory of Belgium <https://www.sidc.be/SILSO/> (monthly mean total, v2.0).
Retrieved 2026-07-14. License: SILSO data, CC BY-NC 4.0.

## Cleaning steps
Parse the semicolon file; the missing-value code `-1` → NaN, dropped; date = first of month.

## TEACHER NOTE
The 11-year cycle is obvious. The punchline: satellite measurements since 1978 show the Sun's output
**flat/slightly declining while temperature rises** — so the Sun's rhythm does **not** explain the trend.
A sunspot-vs-temperature scatter gives a weak/near-zero r.

## Load
```python
import pandas as pd
sun = pd.read_csv("https://raw.githubusercontent.com/Saleh314Astro/data-science-journey-data/main/projects/sunspots/clean.csv", parse_dates=["date"])
```

## Suggested figures
1. Full series showing the ~11-year cycle.
2. Zoom on 3 cycles.
3. Sunspots vs temperature scatter + r (the "maybe it's the Sun" test).
