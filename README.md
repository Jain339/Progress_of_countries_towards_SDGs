# SDG Final Project

## UNICEF Project Exploration – STA130 Winter 2024
### Authors: Nikita Jain, Anish Pai, Anudari Jamsran

## Table of Contents

1. [Project Overview](#project-overview)
2. [Research Questions](#research-questions)
3. [Project Structure](#project-structure)
4. [Data Overview](#data-overview)
5. [Modeling & Analysis](#modeling--analysis)
6. [Visualizations](#visualizations)
7. [Installation & Usage](#installation--usage)
8. [Citations](#citations)

## Project Overview

The project analyzes development progress toward the UN Sustainable Development Goals (SDGs) by comparing landlocked developing countries (LLDCs) and small island developing states (SIDS). Using publicly available datasets from the UN, the study evaluates differences in economic growth, access to clean water, and gender equality outcomes between these two country types.

The goal is to identify actionable insights for accelerating SDG progress in countries with unique geographic and development challenges.

**Guiding Research Question:**
How do landlocked countries compare with small island nations in their advancement toward meeting the UN’s Sustainable Development Goals (SDGs)?

## Research Questions

### **RQ1 – Economic Growth Classification**

* Can countries be classified as having high or low economic growth based on education, labor participation, and unemployment rates?
* Which country type (landlocked vs. small island) yields a more accurate classification?

### **RQ2 – SDG 6: Clean Water Access**

* Are people from landlocked countries using more clean water compared to small island nations?

### **RQ3 – Gender Equality**

* Do countries show higher or lower gender inequality based on their geographic categorization as landlocked or small islands using the Women Empowerment Index?

## Project Structure

The repository contains:

```
SDG-Final-Project/
├── SDG_Final_Project.Rmd           # Complete R Markdown code for analysis
├── SDG_Final_Project.pdf           # PDF output report
├── country_codes.csv               # Country metadata including LLDC and SIDS classification
├── country_indicators.csv          # Country indicators on education, labor, health, and women’s empowerment
├── sdr_fd5e4b5a.csv                # SDG scores dataset
├── Visualizations/                         # Directory for plots and visualizations
└── README.md                       # Project description and instructions
```

## Data Overview

**Datasets Used:**

1. **Country Codes:** Includes ISO codes, geographic classifications (LLDC, SIDS), and development status.
2. **Country Indicators:** Measures of economic empowerment, clean water access, health, education, and gender-related metrics.
3. **SDG Scores:** UN SDG goal scores and indices for 2023 for 17 goals.

**Key Variables:**

* Goal 8 Score: Decent Work and Economic Growth
* Clean Water Usage: Total, urban, and rural
* Women Empowerment Index (WEI): Derived from multiple indicators including education, labor participation, financial inclusion, health, and exposure to violence.


## Data Wrangling and Cleaning

* Filtered for developing countries only.
* Merged country codes with SDG goal scores and indicator datasets.
* Created average metrics for educational attainment, labor participation, and unemployment.
* Computed the Women Empowerment Index (WEI) using normalized indicators for health, education, inclusion, decision-making, and violence.

## Modeling and Analysis

**RQ1 – Classification Trees**

* Built decision tree models to classify countries’ economic growth (`good` vs `bad`) for both landlocked and small island countries.
* Predictors: average educational attainment, labor force participation, and unemployment rate.
* Visualized trees using `partykit` in R.

**RQ2 – Hypothesis Testing**

* Simulated clean water usage data using 10,000 trials.
* Conducted two-sample t-tests comparing landlocked and small island countries.
* Visualized differences using histograms and boxplots.

**RQ3 – Gender Inequality**

* Integrated multiple indicators to calculate WEI.
* Conducted permutation tests to compare mean WEI between landlocked and small island countries.
* Visualized results with histograms and boxplots.

## Visualizations

* Classification trees for economic growth.
* Histograms and boxplots for clean water usage differences.
* Histograms and boxplots for Women Empowerment Index scores.
* All plots are saved in the `images/` folder.

## Installation & Usage

1. Clone the repository:

   ```
   git clone https://github.com/your-username/SDG-Final-Project.git
   cd SDG-Final-Project
   ```
2. Install required R packages:

   ```
   install.packages(c("tidyverse", "rpart", "partykit", "grid", "readr", "dplyr"))
   ```
3. Open and run `SDG_Final_Project.Rmd` in RStudio to reproduce the analysis and generate the PDF report.

## Citations (MLA 9th Edition)

1. Jain-Chandra, Sonali. *Chapter 2. Gender Inequality around the World.* International Monetary Fund.
2. *TOWARDS IMPROVED MEASURES of GENDER INEQUALITY: An Evaluation of the UNDP Gender Inequality Index.* UN Women.
3. *Technical Note: Twin Indices on Women’s Empowerment and Gender Equality.* UNDP.
4. Duflo, Esther. “Women Empowerment and Economic Development.” *Journal of Economic Literature*, vol. 50, no. 4, 2012, pp. 1051–1079.

