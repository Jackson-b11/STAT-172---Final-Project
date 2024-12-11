# Stat-172-Final-Project

## Project Overview

This project, created as part of the Stat-172 course at Drake University, utilizes R to analyze food insecurity in Iowa. Partnering with WesleyLife, a non-profit organization delivering meals to those in need, we aimed to identify areas with high levels of food insecurity. This analysis will help WesleyLife prioritize counties for their planned expansion beyond Polk County.

Using PUMA (Public Use Microdata Area) data, we developed predictive models and visualizations to provide actionable insights.

------------------------------------------------------------------------

## Data Sources

We worked with two primary datasets:

### CPS (Current Population Survey):

-   Collected at the individual level, with additional household information.
-   Includes data on food insecurity but lacks county-level coverage, limiting its standalone applicability.

### ACS (American Community Survey):

-   Census data collected across Iowa, including PUMA-level information.
-   Does not directly measure food insecurity but contains predictors useful for modeling.

------------------------------------------------------------------------

## Methods

### Model Training and Testing

1.  **Predictive Model Setup**: 70% of CPS data was used for training, and 30% for testing.
2.  **Regression Models**: Lasso (alpha = 1) and Ridge (alpha = 0) regressions were employed.
3.  **Cross-Validation**: Optimal penalty parameters (lambda) for each model were determined via cross-validation.
4.  **Evaluation**: ROC curves were generated to assess sensitivity and specificity at different thresholds, comparing AUC (Area Under the Curve) values for both models.

### Model Application

-   The trained models were applied to ACS data to predict food insecurity probabilities at the PUMA level.

### Data Visualization

-   PUMA shapefiles were used to create choropleth maps, displaying:
    -   General food insecurity probabilities.
    -   Focused analysis on elderly populations.

------------------------------------------------------------------------

## How to Use the Code

To replicate our analysis or explore the data:

1.  **Setup**:
    -   Download the R script `model_y1.R` from the `Code` folder.
    -   Download datasets from the `Data` folder.
2.  **Run the Script**:
    -   Open `model_y1.R` in RStudio.
    -   Run the script to reproduce the methods and results.

The script includes comments explaining each step of the analysis.

------------------------------------------------------------------------

## Key Results and Recommendations

Based on the predictions, our recommendations for WesleyLife's expansion are:

1.  **Largest Senior Population**:
    -   **Recommendation**: Dubuque, Buchanan, Jackson & Delaware Counties (Dubuque City PUMA).
2.  **Highest Food Insecurity Probability**:
    -   **Recommendation**: Des Moines, Lee, Henry & Louisa Counties PUMA.
3.  **Combination of Senior Population and Food Insecurity Probability**:
    -   **Recommendation**: Dubuque, Buchanan, Jackson & Delaware Counties (Dubuque City PUMA).

> **Note**: Southwest Iowa—Council Bluffs City PUMA—was excluded as most of its population resides in Omaha, where WesleyLife already has a presence.

------------------------------------------------------------------------

## Conclusions

Our analysis provides a data-driven approach to prioritize expansion efforts, enabling WesleyLife to maximize its impact by targeting areas with the highest need.

------------------------------------------------------------------------

## Acknowledgments

-   Special thanks to WesleyLife for their collaboration.
-   Gratitude to course instructor Lendie Follett for guidance and support.
