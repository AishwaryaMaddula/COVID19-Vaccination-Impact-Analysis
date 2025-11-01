# 🧬 Impact of Vaccinations on COVID-19 Deaths

### **Project Overview**
This project analyzes how COVID-19 vaccination rates influenced death trends across U.S. states during the pandemic. Using public datasets from the CDC and HealthData.gov, we cleaned, merged, and explored the relationships between vaccination rates, case counts, and mortality rates over time. The analysis highlights both state-level and regional patterns to evaluate the real-world impact of vaccination campaigns.

---

### **Objectives**
- Examine how state-level vaccination rates correlate with COVID-19 deaths and cases  
- Understand the timing of vaccine effectiveness (e.g., lag of two weeks)  
- Assess the effect of state policies on mitigating deaths  
- Visualize patterns at both state and regional levels  

---

### **Data Sources**
- **COVID-19 Cases and Deaths:** [usafacts.org](https://usafacts.org/visualizations/coronavirus-covid-19-spread-map/)
- **Vaccination Data:** [cdc.gov](https://www.cdc.gov/coronavirus/2019-ncov/vaccines/index.html)
- **State and County Policy Data:** [healthdata.gov](https://healthdata.gov/dataset/COVID-19-State-and-County-Policy-Orders/gyqz-9u7n/about_data)
- **State and Region Data:** [US Census](https://www2.census.gov/geo/pdfs/maps-data/maps/reference/us_regdiv.pdf)

---

### **Technologies Used**

<p align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/r/r-original.svg" width="40" height="40" alt="R"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/rstudio/rstudio-original.svg" width="40" height="40" alt="RStudio"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/markdown/markdown-original.svg" width="40" height="40" alt="Markdown"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" width="40" height="40" alt="GitHub"/>
  <img src="https://tidyverse.tidyverse.org/logo.png" width="40" height="40" alt="tidyverse"/>
  <img src="https://ggplot2.tidyverse.org/logo.png" width="40" height="40" alt="ggplot2"/>
  <img src="https://dplyr.tidyverse.org/logo.png" alt="dplyr" width="40" height="40"/>
  <img src="https://lubridate.tidyverse.org/logo.png" alt="lubridate" width="40" height="40"/>
</p>


- **R Markdown** for data analysis and report generation  
- **Packages:** `tidyverse`, `lubridate`, `ggplot2`, `dplyr`  
- **Output:** Interactive HTML report via `rmarkdown::render()`  

---

### **Methodology**

1. **Data Cleaning & Preparation**  
   - Standardized dates and state identifiers across datasets  
   - Lagged vaccination data by two weeks to reflect immunity onset  
   - Removed duplicates and handled missing values  
   - Merged datasets using `date` and `state` as primary keys  

2. **Exploratory Data Analysis (EDA)**  
   - Checked for nulls and outliers using IQR-based filtering  
   - Visualized case counts, deaths, and vaccination rates over time  
   - Added regional categorization (West, South, Midwest, Northeast) for comparison  
   - Generated faceted line plots and boxplots to identify outliers and patterns  

3. **Visualization Highlights**
   - **Boxplots:** Showed spread and outliers in case counts per state  
   - **Time Series Plots:** Illustrated daily/weekly vaccination, death, and case trends  
   - **Scatterplots:** Compared vaccination rates with total COVID-19 cases per state  

---

### **Statistical Analysis**

To support visual findings, several statistical techniques were applied to quantify relationships between variables:

1. **Correlation Analysis**
   - Computed Pearson correlation coefficients to measure the strength and direction of relationships between vaccination rates, case counts, and death rates. 
   - Strong negative correlations between vaccination rate and death rate suggested that as vaccine coverage increased, deaths decreased.

2. **Lag Effect Validation**
   - Conducted correlation tests with time-lagged vaccination data (2-week offset) to confirm improved alignment between vaccination rates and subsequent reductions in deaths.

3. **Linear Regression Modeling**  
   - Built multiple linear regression models where COVID-19 deaths were predicted using vaccination rate, policy strictness, and case counts as independent variables. 
   - Model summary and coefficients helped quantify the relative contribution of each predictor.

4. **ANOVA (Analysis of Variance)**  
   - Used ANOVA to determine whether mean death rates differed significantly across regions (West, Midwest, South, Northeast). 
   - Results confirmed statistically significant differences, especially during early vaccination phases.

5. **Residual and Diagnostic Checks**
   - Performed residual analysis to validate assumptions of linear regression (normality, homoscedasticity, and independence).
   - Visualized residual plots to ensure model validity.

Together, these tests provided statistical backing for the observed patterns in the exploratory analysis and supported the conclusion that vaccination coverage played a substantial role in reducing COVID-19 mortality across states.

---

### **Key Insights**
- States with higher vaccination coverage showed slower growth in death rates  
- Lagging vaccine data by two weeks improved correlation accuracy with death trends  
- Regional analysis revealed clear patterns, especially spikes in populous states like California, Texas, and New York  
- Policy interventions coincided with declines in new cases following vaccination peaks  

---

### **Project Output**
The final analytical report is available as an interactive HTML file:  
📄 **[`COVID19-VaccinationImpactAnalysis.html`](Analysis/COVID19-VaccinationImpactAnalysis.html)**  

It includes visualizations, R code chunks, and results demonstrating the complete workflow and findings.

---
