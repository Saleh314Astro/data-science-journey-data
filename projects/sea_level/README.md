# sea_level — "The Rising Ocean / المحيط الصاعد"

**Question:** A witness that shares no thermometer — if the planet warms, the sea must rise. Does it?

## File
- `clean.csv` (date, gmsl_mm) — global mean sea level, millimetres, monthly. 1880–2013.

## Source
CSIRO reconstructed GMSL (Church & White 2011, 2015 update)
<https://www.cmar.csiro.au/sealevel/>. Retrieved 2026-07-11. License: CSIRO, free for research.

## Cleaning steps
Convert decimal time to year+month; keep GMSL (mm); drop the uncertainty column (documented: ±24 mm in
1880 narrowing to ±9 mm by 2013). Reconstruction ends 2013; the satellite era (1993+) can be added as a
stretch.

## Load
```python
import pandas as pd
sea = pd.read_csv("https://raw.githubusercontent.com/Saleh314Astro/data-science-journey-data/main/projects/sea_level/clean.csv", parse_dates=["date"])
```

## Suggested figures
1. Full series (the long rise).
2. Rate before vs after 1993 (is it accelerating?).
3. Overlay with the temperature anomaly — an independent witness agreeing.
