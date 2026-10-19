# SPX Historical-Volatility Regimes and the VIX Short-End Term Structure

A descriptive empirical study of how the **VIX1D–VIX9D–VIX implied-volatility term structure** varies across Low, Normal, and High historical-volatility regimes of the S&P 500 (SPX).

**Author:** Mattia Mancinelli  
**Analytical sample:** February 1, 2023 – September 29, 2026  
**Observations:** 918 trading sessions  
**Approach:** Descriptive regime comparison and sensitivity analysis

## Research Question

> How does the VIX1D–VIX9D–VIX implied-volatility term structure vary across Low, Normal, and High SPX historical-volatility regimes?

## Study Design

The analysis considers three Cboe indices representing the short end of the SPX option-implied volatility term structure:

- **VIX1D:** approximately one-day implied volatility
- **VIX9D:** approximately nine-day implied volatility
- **VIX:** approximately 30-day implied volatility

Market regimes are classified using **historical volatility calculated from SPX daily close-to-close log returns**, rather than from the implied-volatility indices. The baseline specification uses rolling 20-session historical volatility (**HV20**); a rolling 10-session measure (**HV10**) provides an alternative regime classification for descriptive sensitivity analysis. Both measures are annualized using a factor of √252.

Regime thresholds are defined separately for each measure using the 25th and 75th percentiles of the common analytical sample:

| Classification | Low / Normal threshold (P25) | Normal / High threshold (P75) |
| -------------- | ---------------------------- | ----------------------------- |
| HV20 | 10.16% | 14.58% |
| HV10 | 9.42% | 14.95% |

For each classification, the sample contains **230 Low, 458 Normal, and 230 High** observations. These regimes are retrospective and relative to the sample; they are not universal volatility-state thresholds.

## Empirical Methodology

Term-structure shape is examined through:

- **Pairwise spreads:** VIX1D − VIX9D (1D–9D), VIX9D − VIX (9D–30D), and VIX1D − VIX (1D–30D)
- **Ratios:** scale-relative comparisons of implied-volatility index levels
- **Horizon-normalized slopes:** descriptive transformations of the corresponding spreads
- **Spread distributions:** means, medians, quartiles, and interquartile ranges (IQRs)
- **Inversion frequencies:** the share of sessions with positive pairwise spreads, and full inversions defined by VIX1D > VIX9D > VIX

The primary comparisons use **median spread differences relative to the Normal regime** (Low − Normal and High − Normal). The same descriptive analysis is repeated under HV10 to assess sensitivity to the historical-volatility window.

**This study does not use hypothesis tests, bootstrap inference, or confidence intervals.** The reported contrasts describe the observed sample rather than statistically established population relationships.

## Main Findings

Across both HV20 and HV10 classifications:

1. **Implied-volatility levels are higher in higher historical-volatility regimes.** The increases are larger at shorter horizons.
2. **Median pairwise spreads become less negative from Low to High.** This indicates a flatter short-end term structure, although the median of every pairwise spread remains negative in every regime.
3. **The High regime has the largest IQR for each spread.** This indicates greater absolute dispersion in the central half of the spread distributions, without implying that dispersion increases at every intermediate regime transition.
4. **Pairwise and full inversions become more frequent.** Nevertheless, each inversion frequency remains below 50% in every regime.
5. **All six median spread contrasts retain their signs across HV20 and HV10.** Several contrasts differ in magnitude, so directional consistency does not imply quantitative invariance across classification methods.

Selected results for the baseline **HV20** specification illustrate the observed differences:

| Measure | Low regime | High regime |
| ------- | ---------- | ----------- |
| Median 1D–30D spread (index points) | −4.125 | −2.420 |
| 1D–30D inversion frequency | 6.52% | 24.35% |
| Full inversion frequency | 2.17% | 11.74% |

The flattening of median spreads, widening of IQRs, and higher inversion frequencies describe **different features of related distributions**, not independent empirical confirmations.

## Full Paper

📄 [**Read the complete paper**](paper.pdf)

The paper provides the data definitions, methodological choices, descriptive results, economic interpretation, limitations, references, and supplementary figures and statistics.

## Selected Figures

### Average VIX Short-End Term Structure — HV20

![Average VIX Short-End Term Structure — HV20](Figures/figure1a_term_structure_hv20.png)

### Inversion Frequencies — HV20

![Inversion Frequencies — HV20](Figures/figure3a_inversion_frequency_hv20.png)

Additional HV10 figures and spread-distribution boxplots are available in [`Figures/`](Figures/).

## Repository Contents

```text
.
├── Figures/
├── SPX VIX Term Structure Public Analysis.xlsx
├── paper.pdf
├── paper.qmd
├── references.bib
├── chicago-fullnote-bibliography.csl
├── README.md
└── .gitignore
``` 

## Data Sources

The analysis uses publicly available data from:

- **Cboe Global Markets** — VIX1D, VIX9D, and VIX
- **Federal Reserve Bank of St. Louis (FRED)** — S&P 500 Index (SP500)

Full citations and source links are reported in the paper.

## Scope

This is an empirical market-analysis project focused on the relationship between SPX historical-volatility regimes and the configuration of the VIX short-end implied-volatility term structure.

The analysis is descriptive within the observed sample and is not intended as a trading strategy or causal model.
