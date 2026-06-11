# Crude Oil vs Gas Pump Prices (2016–2026)

An interactive, single-file visualization of how US retail gasoline prices track WTI crude oil, quarterly from 2016 through Q2 2026. Built to make the relationship *talk*: annotated event zones, regional comparisons, inflation adjustment, and a pump-spread view that shows where your money at the pump actually goes.

## Demo https://dhruvpolaris.github.io/crude-oil-vs-gas-pump-prices

## Features

- **Dual-axis quarterly chart** — WTI crude ($/bbl) and retail regular gasoline ($/gal), 42 quarters from 2016 Q1 to 2026 Q2 (partial).
- **Region selector** — switch between the US average and the five EIA PADD regions: East Coast, Midwest, Gulf Coast, Rocky Mountain, and West Coast.
- **Inflation toggle** — view prices in nominal dollars or real 2026 dollars (deflated with annual CPI-U). In real terms, the 2022 Ukraine-era peak (~$123/bbl) still tops the 2026 Iran-war spike.
- **Pump spread view** — plots pump price minus crude cost per gallon (WTI ÷ 42). This gap covers refining, distribution, retail margin, and taxes, and tells a different story than prices alone: the COVID quarter appears as a spike, not a dip.
- **Annotated event zones** — four shaded, numbered zones flag the moments that matter, with matching insight cards:
  1. Late 2018 oversupply slide
  2. Q2 2020 COVID demand crash
  3. 2022 Ukraine invasion spike
  4. 2026 Iran war (still unfolding)
- **Live summary cards** — current crude price, regional gas price, and a crude–gas correlation (or average spread) that recalculates as you switch regions and views.
- **Dark mode** — follows the OS `prefers-color-scheme` setting automatically.

## Data sources

| Series | Source |
|---|---|
| Retail gasoline prices (US + PADD regions) | [EIA Gasoline and Diesel Fuel Update](https://www.eia.gov/petroleum/gasdiesel/) and [EIA Weekly Retail Gasoline Prices by region](https://www.eia.gov/dnav/pet/pet_pri_gnd_a_epmr_pte_dpgal_w.htm) |
| WTI crude oil spot prices | [EIA via FRED](https://fred.stlouisfed.org/series/GASREGW) |
| Inflation (CPI-U) | [Bureau of Labor Statistics](https://www.bls.gov/cpi/) |
| 2026 market context | [EIA Today in Energy, Apr 2026](https://www.eia.gov/todayinenergy/detail.php?id=67424) and [Dallas Fed Working Paper 2609](https://www.dallasfed.org/~/media/documents/research/papers/2026/wp2609.pdf) |

## Methodology and caveats

- All values are **quarterly averages**. 2026 Q2 is a partial quarter (April through early June 2026).
- **Regional quarterly values are derived**, not raw: national quarterly prices are scaled by each region's annual EIA differential. This preserves the overall shape and regional level differences, but smooths over region-specific events (e.g., West Coast refinery outages).
- **Real dollars** are deflated to 2026 using annual CPI-U averages, applied uniformly within each year.
- The **pump spread** here is the full retail spread (pump price − crude cost per gallon). It is not the industry "crack spread," which refers specifically to the refiner's margin (wholesale product price − crude, typically quoted as the 3-2-1 spread).
- 2026 figures were compiled mid-spike during the Iran war and will shift as the year completes.

## Tech stack

- [Chart.js 4](https://www.chartjs.org/) with the [annotation plugin](https://www.chartjs.org/chartjs-plugin-annotation/) for the event zones
- Vanilla HTML/CSS/JS — no framework, no build tooling
- [Inter](https://fonts.google.com/specimen/Inter) via Google Fonts

## Repo structure

```
.
├── crude-oil-vs-gas-prices.html
└── README.md
```

## License

Data is from public US government sources (EIA, BLS, FRED).
