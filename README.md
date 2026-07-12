# data-science-journey-data

Public, ready-to-load climate datasets for the course
**A Journey Through Data Science** (Mawhiba × KSU).

Load any file in one line — works in Colab, Binder, or locally:

```python
import pandas as pd
base = "https://raw.githubusercontent.com/Saleh314Astro/data-science-journey-data/main/"
df = pd.read_csv(base + "clean/gistemp_monthly.csv", parse_dates=["date"])
df.head()
```

## `clean/` — tidy two-column files (`date`, `value`)
| file | source | units | span |
|---|---|---|---|
| `gistemp_monthly.csv` | NASA GISTEMP v4 | °C anomaly vs 1951–1980 | 1880–2026 |
| `keeling_co2_monthly.csv` | NOAA Mauna Loa | ppm | 1958–2026 |
| `nsidc_seaice_monthly.csv` | NSIDC Sea Ice Index v4 (Arctic) | million km² | 1978–2026 |
| `sealevel_monthly.csv` | CSIRO (Church & White) | mm | 1880–2013 |

`date` is the first day of each month (a month label, not a measurement day).

## `raw/` — the original published files, untouched
Headers, footnotes, and missing-value codes intact — for the "reproduce the clean
file" challenge. All sources are public-domain (NASA / NOAA / NSIDC) or CSIRO.
