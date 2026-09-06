# Brent oil price analysis
Data analysis and econometric modeling of Brent crude oil prices using Python, OLS regression, correlation analysis, VIF, and Power BI.
## Project Overview

This project investigates whether changes in global oil demand, Saudi Arabian oil production, UAE oil production, and the nominal US Dollar Index are associated with changes in the average annual Brent crude oil price.

The analysis covers annual observations from 2005 to 2025.

## Libraries & Tools

### Python Libraries

- **Pandas** — used for data loading, cleaning, transformation, merging, aggregation, correlation analysis, and creating analytical tables.
- **NumPy** — used for numerical operations, including fitting the linear trend line for the Brent–USD relationship and handling missing numerical values.
- **Matplotlib** — used to create visualizations of Brent price dynamics, factor relationships, regression diagnostics, and VIF results.
- **Scikit-learn** — used for pairwise linear regression and for the auxiliary regressions required to calculate VIF.
- **Statsmodels** — used for the final OLS regression and statistical inference, including coefficients, standard errors, t-statistics, p-values, the F-test, and model diagnostics.

### BI Tool

- **Power BI** — used to create the final interactive dashboard and present the key analytical results.
## Research Hypotheses

### H1
Higher Saudi Arabian oil production is associated with lower average annual Brent prices.
### H2
Higher UAE oil production is associated with lower average annual Brent prices.
### H3
Higher global oil demand is associated with higher average annual Brent prices.
### H4
A stronger nominal US Dollar Index is associated with lower average annual Brent prices.
### H5
Global oil demand has a stronger association with Brent prices than oil production in Saudi Arabia and the UAE.
### H6
The association between Saudi Arabian oil production and Brent prices is stronger than that between UAE oil production and Brent prices.

## Limitations

The analysis is based on only **21 annual observations**, which limits the statistical power of the estimated models.

The results represent statistical associations rather than direct causal relationships.

Multicollinearity is present among some explanatory variables and may affect the stability and interpretation of individual regression coefficients.

The 2005 nominal US Dollar Index value was manually assigned as 98 because the available DXY dataset starts in 2006.

## Key Results

The multiple OLS regression explains approximately **56.5%** of the variation in average annual Brent prices.

**R^2 = 0.565**

The overall regression model is statistically significant:

**F-statistic = 5.20**  
**F-test p-value = 0.007**

### Individual predictors

| Variable | Coefficient | P-value | Result |
|---|---:|---:|---|
| Global oil demand | +4.43 | 0.016 | Significant |
| Saudi oil production | +1.69 | 0.874 | Not significant |
| UAE oil production | -16.73 | 0.723 | Not significant |
| Nominal US Dollar Index | -2.78 | <0.001 | Significant |

> Production and demand coefficients are expressed per 1 million barrels/day. The DXY coefficient is expressed per index point.

## VIF Analysis

The VIF analysis indicates multicollinearity among some explanatory variables.

| Variable | VIF |
|---|---:|
| World Demand | 10 |
| Saudi Production | 4 |
| UAE Production | 12 |
| Dollar Index | 4 |

The highest VIF values are observed for global oil demand and UAE production, indicating that their coefficients should be interpreted with caution.

## Hypothesis Results

| Hypothesis | Result |
|---|---|
| H1 — Saudi production ↑ → Brent ↓ | ❌ Not supported |
| H2 — UAE production ↑ → Brent ↓ | ❌ Not supported |
| H3 — Global demand ↑ → Brent ↑ | ✅ Supported |
| H4 — DXY ↑ → Brent ↓ | ✅ Supported |
| H5 — Global demand has a stronger association | ⚠️ Inconclusive |
| H6 — Saudi production has a stronger association than UAE production | ❌ Not supported |

## Visual Analysis

The project also includes a Power BI dashboard presenting:

- Brent price dynamics from 2005 to 2025
- OLS regression results
- statistically significant and insignificant factors
- hypothesis results
- VIF diagnostics

## Data

The project uses publicly available data on:

- Brent crude oil prices
- Saudi Arabian crude oil production
- UAE crude oil production
- Global oil demand
- Nominal US Dollar Index
