# Remittance Dependence and Economic Vulnerability in Nepal: A Comparative Analysis, 2000–2024

Nepal receives personal remittances equal to roughly a quarter of its GDP — one of the highest ratios in the world. This notebook asks whether that remittance-driven economic performance represents genuine development, or whether it masks weak domestic job creation, using a comparative analysis against three other remittance-dependent economies.

**Relevant SDGs:** SDG 1 (No Poverty), SDG 8 (Decent Work and Economic Growth), SDG 10 (Reduced Inequalities)

## Research questions

**Primary:** How has Nepal's increasing dependence on remittances been associated with economic growth, labor-market participation, poverty, and external-sector stability between 2000 and 2024?

- **RQ1 (Dependence):** How has Nepal's remittance dependence evolved relative to peer economies?
- **RQ2 (Growth):** Is increasing remittance dependence associated with stronger GDP growth in Nepal?
- **RQ3 (Labor market):** Is remittance dependence associated with lower labor-force participation?
- **RQ4 (Poverty & external balance):** How does remittance dependence coincide with poverty and current-account trends?

## Data

- **Source:** World Bank World Development Indicators (WDI), accessed via the `wbgapi` Python package
- **Period:** 2000–2024
- **Countries:** Nepal (focus), Bangladesh, Sri Lanka (South Asian peers), Philippines (out-of-region comparator)
- **Unit of analysis:** country-year observations
- **Indicators:** personal remittances (% of GDP), GDP growth, poverty headcount ratio ($2.15/day), labor force participation (total, female, male), current account balance, gross capital formation, FDI net inflows, exports, imports, household consumption

## Methodology

- Descriptive statistics by country
- Time-series trend analysis
- Pooled and country-specific ("within-country") Pearson correlation, to separate between-country from within-country patterns
- Exploratory univariate regression (r, R², slope, p-value — explicitly not causal)
- Correlation matrices (pooled vs. Nepal-only)

## Key findings

- Nepal's remittance-to-GDP ratio rose from roughly 3% (2000) to 26–28% (mid-2010s–2020s), overtaking all three comparator countries by around 2007–2008.
- **Growth:** Nepal-only correlation between remittances and GDP growth is essentially null (r = -0.026, p = 0.90) — remittance income and the domestic growth cycle moved independently.
- **Labor force participation:** Nepal's within-country correlation (r = -0.737, p < 0.0001) is *stronger* than the pooled correlation (r = -0.696) — contradicting the initial hypothesis that this was a between-country artifact. Sri Lanka and the Philippines show positive correlations instead, so this pattern doesn't generalize across peers.
- **Poverty:** Nepal's poverty headcount ratio fell from 55.9% (2003) to 2.4% (2022), a 53.5 percentage-point drop — the clearest finding in the analysis, coinciding with the period of rising remittances.
- **External balance:** No significant relationship between remittances and current account balance at the annual level (r = 0.054, p = 0.80).

See the notebook's **Key Findings**, **Policy Implications**, and **Limitations** sections for full discussion, caveats, and confidence levels.

## Limitations

- All relationships are correlational, not causal
- Small country sample (n = 4)
- Poverty headcount data has substantial gaps (survey years only)
- No controls for omitted variables (domestic investment shocks, migration policy changes, global remittance-corridor conditions)

## Getting started

```bash
pip install wbgapi pandas numpy matplotlib seaborn scipy
jupyter notebook Nepal_Remittance_Analysis_.ipynb
```

Run all cells in order — the notebook pulls data live from the World Bank API via `wbgapi`, so an internet connection is required.

## References

- World Bank, World Development Indicators (WDI) database, accessed via the `wbgapi` Python package
- Indicator definitions: World Bank DataBank metadata for each series code used
