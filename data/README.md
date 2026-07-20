# Data (not committed)

The real franchise dataset is **not included** in this repository — it's client/coursework data. To run the dashboard, place the following files in this `data/` folder. The app loads them client-side (see the loader functions in `../script.js`).

| File | Used by | Contents (high level) |
|---|---|---|
| `owner_rankings.csv` | Risk module | one row per franchise owner (~688) with overall risk score / class / ranking |
| `owner_store_map.csv` | Risk module | mapping of owners → their stores |
| `store_monthly_risk.csv` | Risk module | one row per store per month (~32,000 rows across 4,886 stores) with the 19 risk flags |
| `data.db` | Top performance chart (teammate) | SQLite database read in-browser via sql.js |

The 19 risk flags and their plain-English definitions are documented in the `FLAG_GLOSSARY` object at the top of `../script.js`.
