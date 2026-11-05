# Theft Trends in Colombia: Annual Trend and Seasonality

Has reported theft in Colombia gone up or down over the last 15 years, and are some months consistently worse than others? This project answers both questions with 44,169 theft records published by Colombia's National Police.

**Tools:** R · tidyverse · lubridate · janitor · ggplot2 · R Markdown
**Methods:** exploratory analysis, linear regression, one-way ANOVA

## Key findings

| Question | Result |
|---|---|
| Is there a linear trend, 2011–2025? | No. Slope −66 cases/year, p = 0.379, R² = 0.06 |
| What does the series actually do? | Rises from 1,884 cases (2011) to a peak of 5,741 (2017), then falls to 957 (2025), the lowest in the series |
| Is there monthly seasonality? | No. ANOVA F = 0.444, p = 0.934 |

- A straight-line model is the wrong description of this data: the series is **rise-then-decline** around 2017, which is why the regression fits poorly.
- January has the highest monthly total (about 4,100 cases) and October–December are slightly lower (about 3,200), but the difference is small next to year-to-year variation.
- **Livestock theft (*abigeato*) is about 85% of the records.** That explains why the departments with the most cases are rural and agricultural (Cundinamarca, Cesar, Tolima, Antioquia, Meta) and why most victims are men (about 31,000 vs. 7,000).

## Data

**Reporte Hurto por Modalidades Policía Nacional**, from [Datos Abiertos Colombia](https://www.datos.gov.co), provided by the Dirección General de la Policía Nacional (DIPON). Included here as `hurtos.csv`.

The file covers three theft types only: livestock theft (37,548 rows), highway robbery (*piratería terrestre*, 4,841) and theft from financial institutions (1,780). The conclusions apply to these types, not to all theft in Colombia. Records run from January 2010 to March 2026; 2010 and 2026 are excluded from the trend and seasonality tests because they are incomplete years.

## How to run

Open `theft_analysis_colombia.Rmd` in RStudio with `hurtos.csv` in the same folder and knit to PDF or HTML. Packages:

```r
install.packages(c("tidyverse", "lubridate", "janitor"))
```

## Limitations

Official police reports undercount unreported crime, and this dataset excludes theft from persons, homes and vehicles, which the police publish separately.

## Author

Santiago Toro · B.S. Business Data Analytics and Data Science, Arizona State University · [LinkedIn](https://www.linkedin.com/in/santiago-toro-bohorquez)
