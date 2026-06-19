# Data Dictionary

## Dataset Overview

This dataset contains country-level indicators used to analyze the relationship between business environment quality and foreign direct investment inflows.

The dataset focuses on 2019, which represents the pre-COVID global economic environment and helps avoid major distortions caused by the pandemic.

### Dataset Summary

| Metric | Value |
|--------|-------|
| Unit of Analysis | Country |
| Year | 2019 |
| Number of Countries | 171 |
| Number of Variables | 8 |
| Data Type | Cross-sectional country-level data |
| Main Data Sources | World Bank, World Development Indicators, Worldwide Governance Indicators |

---

## Variables

| Variable | Short Name | Type | Measurement | Description |
|----------|------------|------|-------------|-------------|
| Country Name | country | Identifier | Country name | Name of the country included in the dataset. |
| Foreign direct investment, net inflows (current US$) | fdi | Dependent Variable | Current US$ | Net inflows of foreign direct investment. This is the main outcome variable used to measure how much foreign capital a country attracts. |
| Ease of doing business score (0 = lowest performance to 100 = best performance) | eodb | Main Explanatory Variable | Score, 0–100 | Measures how favorable the regulatory environment is for starting and operating a business. Higher values indicate better business conditions. |
| GDP per capita | gdp | Control Variable | Current US$ | GDP per capita, used as a proxy for income level, market development, and economic attractiveness. |
| Unemployment, total (% of total labor force) | unemployment | Control Variable | Percentage of labor force | Share of the labor force that is unemployed. Used to reflect labor market conditions. |
| Urban population (% of total population) | urban | Control Variable | Percentage of total population | Share of population living in urban areas. Used as a proxy for infrastructure, market density, and urban development. |
| Political Stability and Absence of Violence/Terrorism | political | Control Variable | Governance score | Measures perceptions of political stability and absence of politically motivated violence or terrorism. |
| Control of Corruption | corruption | Control Variable | Governance score | Measures perceptions of the extent to which public power is not used for private gain. Higher values indicate stronger corruption control. |

---

## Analytical Variables Used in R

In the R analysis, the original variable names were shortened for easier modeling.

| Original Column | R Variable Name |
|----------------|-----------------|
| Country Name | country |
| Foreign direct investment, net inflows (current US$) | fdi |
| Ease of doing business score (0 = lowest performance to 100 = best performance) | eodb |
| GDP per capita | gdp |
| Unemployment, total (% of total labor force) | unemployment |
| Urban population (% of total population) | urban |
| Political Stability and Absence of Violence/Terrorism | political |
| Control of Corruption | corruption |

---

## Variable Roles in the Model

### Dependent Variable

| Variable | Role |
|----------|------|
| fdi | Main outcome variable. Used to measure the volume of foreign direct investment inflows attracted by each country. |

### Main Explanatory Variable

| Variable | Role |
|----------|------|
| eodb | Main variable of interest. Used to test whether a more favorable business environment is associated with higher FDI inflows. |

### Control Variables

| Variable | Role |
|----------|------|
| gdp | Controls for income level and economic development. |
| unemployment | Controls for labor market conditions. |
| urban | Controls for urbanization and infrastructure-related development. |
| political | Controls for institutional and political stability. |
| corruption | Controls for governance quality and corruption-related risks. |

---

## Data Processing Notes

The dataset was used for econometric analysis in R.

Main processing steps included:

- renaming columns for easier analysis;
- descriptive statistics;
- outlier investigation;
- logarithmic transformation of FDI;
- logarithmic transformation of Ease of Doing Business;
- regression modeling with heteroskedasticity-robust standard errors.

Because FDI inflows are highly skewed and may include negative values, log-transformed models use only observations with positive FDI values.

---

## Data Privacy

The dataset contains only publicly available country-level macroeconomic and institutional indicators.

No personal, confidential, or sensitive individual-level data are included.
