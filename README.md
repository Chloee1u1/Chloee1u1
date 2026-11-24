# Portfolio Risk Modelling Using ARMA-GARCH and Copula Models

This project analyses the risk of an equally weighted portfolio of the S&P 500 and CAC 40 stock indices using weekly closing-price data from 1 January 2000 to 31 December 2025.

## Project overview

The report develops a modelling and simulation workflow for the two financial return series:

1. **Data preparation and exploratory analysis** – prepares the weekly index data, calculates log returns and examines volatility clustering.
2. **Time-series modelling** – uses Box–Jenkins diagnostics and compares AR(1)-GARCH(1,1) models under alternative conditional distributions.
3. **Model diagnostics** – assesses standardised residuals and applies the Probability Integral Transform (PIT), Kolmogorov–Smirnov and Anderson–Darling tests.
4. **Dependence modelling** – selects a copula to model the dependence between the two indices and performs bivariate Monte Carlo simulation.
5. **Simulation and risk measurement** – reintroduces time-series effects, compares simulated and observed returns, and estimates portfolio Value-at-Risk (VaR) at the 95% and 99% confidence levels.

The report presents a one-week portfolio VaR estimate of 2.28% at 95% confidence and 3.83% at 99% confidence.

## Files

- `portfolio_risk_modelling.Rmd` – the R Markdown report, including the analysis, code, tables and figures.
- `S&P500_CAC40.csv` – input data required by the report. This data file is referenced by the R Markdown document and must be placed in the working directory before knitting; it is not included in this repository unless added separately.

## Requirements

The analysis uses R and the following packages:

- `tidyverse`
- `VineCopula`
- `fGarch`
- `KScorrect`
- `ADGofTest`
- `fBasics`
- `kableExtra`
- `pacman`, `knitr` and `rmarkdown` for package loading and report rendering

The setup chunk uses `pacman::p_load()` to load the analysis packages.

## Run the report

1. Install R and, optionally, RStudio.
2. Place `S&P500_CAC40.csv` in the project working directory.
3. Open `portfolio_risk_modelling.Rmd` in RStudio.
4. Knit the document to HTML or PDF. PDF output may require a LaTeX distribution.

## Notes

The report is an academic modelling exercise. Its VaR estimates depend on the data, model specification and simulation procedure described in the report; they should not be interpreted as investment advice.
