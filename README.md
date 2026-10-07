# Franchise BI Risk Dashboard — Risk Analysis Module

> An interactive business-intelligence dashboard that surfaces financial and operational distress across a franchise network of ~4,900 stores. This repository contains the **Risk Results Summary module** I designed and built.

![JavaScript](https://img.shields.io/badge/JavaScript-vanilla-yellow) ![Chart.js](https://img.shields.io/badge/Chart.js-viz-ff6384) ![License: MIT](https://img.shields.io/badge/License-MIT-green)

## Overview

The dashboard answers one operational question: **which franchise owners and stores show financial-distress signals, and what's causing them?** It flags store-level risk (sales decline, low cash flow, high labor cost, rent-vs-profit, and category spend outliers) so a regional-operations team can prioritize interventions.

- **Scope of this module:** 688 franchise owners · 4,886 stores · ~32,000 store-months · 19 risk indicators.
- **Built with:** vanilla JavaScript, HTML, CSS, and Chart.js — no framework, no backend server (data loaded client-side from CSVs).

## What I built (the Risk Results Summary)

Six interactive, dynamically-rendered views, all updating in real time with no page reloads:

1. **Network summary bar** — portfolio-level risk snapshot across all stores.
2. **Top At-Risk Owners leaderboard** — searchable, flag-filterable, with a Top-N selector and pagination; click any row to inspect.
3. **Owner intelligence panel** — per-owner risk probability, a **risk-flag frequency breakdown with plain-English glossary tooltips**, risk-trajectory badges, and per-store cards (with outlier and comparison controls).
4. **Store monthly drill-down** — a 12-month risk-trend bar chart and a month-by-month flag log.
5. **Store comparison** — side-by-side comparison of up to two stores.
6. **Network flag heatmap** — the top flags across all 4,886 stores by month, each row scaled to its own max so seasonal patterns stand out.

Supporting logic includes a **flag glossary**, **risk classification**, **trajectory computation**, **flag co-occurrence analysis**, live search, and flag filtering — roughly 1,000 lines of JavaScript (`script.js`, the risk section) plus the risk-module styling (`styles_additions.css`).

## Team context

Built for **MIS 4400 (Spring 2026)** at Michigan Technological University as a multi-team analytics project for the client "Nova." I built the **Risk Results Summary module** (everything described above). The top performance chart at the top of the page (SQLite + Chart.js) was built by a teammate and is included here for context — it's clearly marked in the code (`// TOP DASHBOARD — unchanged`). The dashboard was an academic deliverable and was not deployed to production.

## Running locally

The app loads data client-side, so it needs a local web server (not `file://`):

```bash
python -m http.server 8000
# then open http://localhost:8000
```

It expects a `data/` folder with the datasets described in [`data/README.md`](data/README.md). The real franchise data is **not committed** (it's client/coursework data); supply your own CSVs matching the documented schema.

## Repository Structure

```
.
├── index.html              # page layout (top chart + Risk Results Summary)
├── script.js               # all logic; the risk module is ~lines 314–1240
├── styles_additions.css    # risk-module styling
├── data/
│   └── README.md           # expected data files + schema (real data withheld)
├── LICENSE
└── README.md
```

## License
MIT — see [LICENSE](LICENSE).
