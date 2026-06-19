# FDI Investment Attractiveness Analysis

## Executive Summary

This project analyzes which country-level factors are associated with higher foreign direct investment (FDI) inflows.

Using 2019 cross-country data from the World Bank and Worldwide Governance Indicators, the analysis tests whether countries with a more favorable business environment attract more FDI. The project applies descriptive statistics, outlier treatment, log transformations, OLS regression, robust standard errors, and interaction models.

The strongest model specification shows that Ease of Doing Business is positively associated with FDI inflows after controlling for GDP per capita, unemployment, urbanization, political stability, and corruption control. The results also suggest that governance factors can change how strongly business environment quality is associated with FDI attraction.

The project demonstrates an end-to-end econometric workflow: from data preparation and exploratory analysis to model comparison, interpretation, limitations, and policy-oriented recommendations.

---

## Business Problem

Countries compete for foreign direct investment because FDI can support economic growth, job creation, technology transfer, and capital inflows.

However, attracting FDI is not determined by one factor alone. Investors may consider:

- regulatory quality;
- ease of doing business;
- income level and market potential;
- unemployment and labor market conditions;
- urbanization and infrastructure availability;
- political stability;
- corruption control.

The business problem addressed in this project is:

**Which country-level factors are most strongly associated with FDI inflows, and how can countries improve their investment attractiveness?**

---

## Research Question

**How does a country's level of Ease of Doing Business affect the volume of foreign direct investment inflows?**

Additional analytical questions:

- Does the relationship remain significant after adding macroeconomic and institutional controls?
- Do political stability and corruption control moderate the relationship between Ease of Doing Business and FDI?
- Which model specification provides the most useful interpretation for investment attractiveness analysis?

---

## Dataset

The analysis uses country-level data for 2019.

2019 was selected because it reflects the pre-COVID global economic environment and avoids major distortions caused by the pandemic.

### Data Sources

- World Bank Open Data
- World Development Indicators
- Worldwide Governance Indicators
- Ease of Doing Business indicators

### Final Analytical Sample

- 171 countries
- 7 main variables

### Variables

| Type | Variable | Description |
|------|----------|-------------|
| Dependent Variable | FDI inflows | Foreign direct investment, net inflows, current US$ |
| Main Explanatory Variable | Ease of Doing Business | Business environment score from 0 to 100 |
| Control Variable | GDP per capita | Economic development indicator |
| Control Variable | Unemployment | Total unemployment rate |
| Control Variable | Urbanization | Urban population as % of total population |
| Control Variable | Political Stability | Political Stability and Absence of Violence/Terrorism |
| Control Variable | Control of Corruption | Governance and corruption control indicator |

---

## Methodology

### 1. Data Preparation

The analysis included:

- importing country-level data from Excel;
- renaming variables for easier analysis;
- checking missing values;
- detecting extreme observations;
- removing selected outliers;
- creating logarithmic transformations for skewed variables.

FDI inflows were strongly right-skewed, so log transformation was used to improve model interpretability and reduce the influence of extreme values.

---

### 2. Exploratory Data Analysis

The EDA stage included:

- descriptive statistics;
- scatterplots;
- histograms;
- boxplots by quartiles;
- correlation matrix.

Key observations from the exploratory stage:

- FDI inflows were highly skewed;
- higher Ease of Doing Business scores were generally associated with higher FDI inflows;
- several countries had extreme FDI values that could distort linear regression results;
- Ease of Doing Business was correlated with institutional and economic variables, requiring careful model interpretation.

---

### 3. Econometric Modeling

Several model specifications were tested.

| Model | Specification | Purpose |
|-------|--------------|---------|
| Simple OLS | FDI ~ EoDB | Tests the direct relationship between business environment and FDI |
| Baseline Model | FDI ~ EoDB + Controls | Adds macroeconomic and institutional controls |
| Log-Lin Model | log(FDI) ~ EoDB + Controls | Addresses skewness in FDI and improves interpretability |
| Log-Log Model | log(FDI) ~ log(EoDB) + Controls | Tests proportional changes in business environment |
| Interaction Model 1 | log(FDI) ~ EoDB × Political Stability | Tests whether political stability changes the effect of EoDB |
| Interaction Model 2 | log(FDI) ~ EoDB × Corruption Control | Tests whether corruption control changes the effect of EoDB |

All regression models used heteroskedasticity-robust standard errors.

---

## Key Findings

### 1. Ease of Doing Business is positively associated with FDI

The simple OLS model showed a positive and statistically significant relationship between Ease of Doing Business and FDI inflows.

However, the explanatory power of the simple model was low, meaning that Ease of Doing Business alone cannot explain cross-country differences in FDI.

---

### 2. Log-transformed models performed better

The Log-Lin model provided the strongest practical specification.

After transforming FDI into logarithmic form, Ease of Doing Business remained statistically significant, while the model's explanatory power increased substantially.

This confirms that handling skewed economic data properly is critical for reliable interpretation.

---

### 3. Macroeconomic and institutional controls matter

The results show that FDI attraction is associated not only with business regulation, but also with broader country-level conditions, including:

- GDP per capita;
- urbanization;
- unemployment;
- political stability;
- corruption control.

This supports the idea that investment attractiveness is multidimensional.

---

### 4. Governance factors affect the strength of the relationship

Interaction models suggest that the effect of Ease of Doing Business on FDI can depend on institutional conditions.

Political stability and corruption control may strengthen or weaken the relationship between business reforms and investment attraction.

---

### 5. Some results require careful interpretation

Political stability and corruption control produced unexpected negative coefficients in some model specifications.

This does not mean that instability or corruption attracts investment. More likely explanations include:

- omitted variable bias;
- sample composition;
- differences between developed and developing economies;
- multicollinearity between institutional indicators;
- the cross-sectional nature of the dataset.

This limitation is explicitly acknowledged in the project.

---

## Business and Policy Implications

The results suggest that improving Ease of Doing Business can help countries become more attractive to foreign investors, but regulatory reform alone is not enough.

Countries seeking to increase FDI should focus on a broader investment-attractiveness strategy:

- simplify administrative and regulatory procedures;
- improve transparency and predictability;
- strengthen institutional quality;
- reduce corruption-related uncertainty;
- develop urban and economic infrastructure;
- improve macroeconomic stability.

For analysts and policy teams, the project demonstrates how econometric modeling can support investment climate assessment and evidence-based policy recommendations.

---

## Limitations

The project has several important limitations:

- The analysis is based on one year only: 2019.
- The models identify associations, not causal effects.
- Some relevant factors were not included, such as infrastructure quality, tax policy, trade openness, labor skills, and exchange rate stability.
- Sector-level FDI differences are not captured.
- Results may differ between developed and developing economies.
- The analysis does not account for long-term dynamics or post-COVID changes.

Future extensions could use panel data, regional segmentation, sector-level FDI data, or causal inference methods.

---

## Tools Used

- R
- RStudio
- Excel
- tidyverse
- ggplot2
- dplyr
- readxl
- fixest
- modelsummary
- GGally

---

## Skills Demonstrated

| Data Analysis | Econometrics | Business Analytics | Research & Strategy |
|--------------|--------------|-------------------|--------------------|
| Data Cleaning | OLS Regression | Investment Attractiveness Analysis | Problem Structuring |
| Exploratory Data Analysis | Multiple Regression | Macroeconomic Analysis | Literature-Based Framing |
| Outlier Treatment | Log Transformations | Policy-Oriented Insights | Critical Interpretation |
| Data Visualization | Interaction Effects | Quantitative Decision Support | Limitations Assessment |
| Correlation Analysis | Robust Standard Errors | Business Environment Assessment | Recommendation Development |

---

## Repository Structure

```text
data/
├── fdi_country_data_2019.xlsx
├── DATA_DICTIONARY.md

fdi_econometric_analysis_output.pdf
full_research_report.pdf
project_presentation.pdf
README.md
```

---

## Files

| File | Description |
|------|-------------|
| `data/fdi_country_data_2019.xlsx` | Country-level dataset used for the analysis |
| `data/DATA_DICTIONARY.md` | Variable descriptions and measurement details |
| `fdi_econometric_analysis_output.pdf` | RStudio / R Markdown analysis output with code, models, tables, and visualizations |
| `full_research_report.pdf` | Full written research report |
| `project_presentation.pdf` | Presentation version of the project |

---

## Author

**Maksim Dumanov**

HSE University — International Programme in Business and Economics

Research Areas: Business Analytics • Data Analytics • Econometrics • Strategy • Investment & Market Research
