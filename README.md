# SPX Historical-Volatility Regimes and the VIX Short-End Term Structure

Empirical analysis of how the VIX1D–VIX9D–VIX implied-volatility term structure varies across Low, Normal, and High historical-volatility regimes of the S&P 500.

**Author:** Mattia Mancinelli  
**Sample:** January 2023 – September 2026  
**Observations:** 918 trading sessions

## Research Question

> How does the VIX1D–VIX9D–VIX implied-volatility term structure vary across Low, Normal, and High SPX historical-volatility regimes?

## Overview

The project studies the short end of the VIX term structure using three Cboe implied-volatility indices:

- **VIX1D** — approximately 1-day expected volatility
- **VIX9D** — approximately 9-day expected volatility
- **VIX** — approximately 30-day expected volatility

Market regimes are defined independently from these indices using rolling historical volatility of daily S&P 500 returns.

The baseline classification uses **20-session historical volatility (HV20)**, while **10-session historical volatility (HV10)** is used as an alternative specification for robustness analysis.

## Methodology

SPX daily log returns are used to calculate annualized HV20 and HV10.

For each historical-volatility measure, observations are classified into:

- **Low:** below the 25th percentile
- **Normal:** between the 25th and 75th percentiles
- **High:** above the 75th percentile

The VIX short-end term structure is then examined through:

- 1D–9D, 9D–30D, and 1D–30D spreads
- Term-structure ratios
- Horizon-normalized slopes
- Distributional dispersion
- Pairwise and full inversion frequencies

Statistical inference is restricted to differences in median spreads and uses a **Moving Block Bootstrap with 10,000 replications and 10-session blocks**.

## Main Findings

The analysis documents a consistent descriptive relationship between SPX historical-volatility regimes and the VIX short-end term structure.

As historical-volatility regimes move from Low to High:

- VIX1D, VIX9D, and VIX levels increase.
- Differences between short- and longer-horizon implied volatility narrow.
- The short-end term structure becomes progressively flatter.
- Spread distributions become wider in the High regime.
- Pairwise and full inversions become more frequent.

The direction of these patterns is preserved under both HV20 and HV10.

Inferential evidence is less uniform. Under the baseline HV20 classification, only one of six median-spread confidence intervals excludes zero, compared with five of six under HV10. This difference does not establish that HV10 is statistically superior.

The results document an association within the observed sample and do not establish a causal mechanism.

## Paper

📄 **[Read the full paper](paper.pdf)**

The paper contains the complete methodology, empirical results, discussion, limitations, references, and appendix.

## Selected Figures

### Average VIX Short-End Term Structure — HV20

![Average VIX short-end term structure under HV20 regimes](Figures/figure1a_term_structure_hv20.png)

### Inversion Frequency — HV20

![VIX term-structure inversion frequency under HV20 regimes](Figures/figure3a_inversion_frequency_hv20.png)

## Repository Structure

```text
.
├── Figures/                         # Figures used in the paper
├── paper.pdf                        # Final paper
├── paper.qmd                        # Quarto source document
├── references.bib                  # Bibliographic database
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
