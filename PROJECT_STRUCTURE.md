# Project: Change Point Analysis and Statistical Modelling of Brent Oil Prices

## Overview

This project analyzes how major geopolitical and economic events impact Brent oil prices using Bayesian Change Point models. The workflow includes data preparation, event research, statistical modeling, and communication of insights via dashboards and reports.

## Folder Structure

- `data/` : Raw and processed Brent oil price data
- `event_data/` : Structured dataset of key events affecting oil prices
- `notebooks/` : Jupyter notebooks for exploratory analysis and modeling
- `scripts/` : Python scripts for data processing and modeling
- `reports/` : Final reports and interim solutions
- `dashboard/` : Interactive dashboard for stakeholders
- `references/` : Key academic and industry references

## Workflow

1. **Data Preparation**: Load and clean Brent oil price data.
2. **Event Research**: Compile a list of major events (political, economic, OPEC decisions) with dates.
3. **Exploratory Analysis**: Analyze time series properties (trend, stationarity).
4. **Modeling**: Apply Bayesian Change Point detection (PyMC3) to identify structural breaks.
5. **Event Association**: Link detected change points to researched events.
6. **Quantitative Impact**: Measure and report the impact of events on price changes.
7. **Communication**: Prepare clear reports and dashboards for stakeholders.

## Assumptions & Limitations

- Statistical correlation does not prove causality.
- Event dates are approximate and may not capture all market influences.
- Model outputs are subject to data quality and chosen priors.

## Communication Channels

- Reports (PDF, Markdown)
- Interactive dashboard (web-based)
- Presentations to government bodies and stakeholders

## References

- PyMC3 documentation
- Academic papers on Bayesian Change Point analysis
- Industry reports on Brent oil market

---

For details, see the README and reference materials in the `references/` folder.
