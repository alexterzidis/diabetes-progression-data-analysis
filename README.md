# Understanding Diabetes Progression

**Final project, Scenario 1 – Data Analytics and Statistics with Applications (LEAP)**

## Research question

Which patient characteristics are associated with diabetes progression, what do regression models tell us, and what conclusions can reasonably be drawn from the data?

## Data

The dataset contains 442 patients with diabetes. For each patient, ten characteristics were measured at the start (age, sex, BMI, average blood pressure and six blood measurements, s1 to s6), together with a measure of disease progression one year later.

Source: [diabetes.tab.txt (NCSU)](https://www4.stat.ncsu.edu/~boos/var.select/diabetes.tab.txt)

The data have no missing values or duplicated rows. Sex is coded as 1 and 2 and was treated as a categorical variable. Because these are health data, results are interpreted with care and are not presented as causal.

## Analysis workflow (in R)

1. Import and check the data (structure, missing values, duplicates)
2. Exploratory analysis (descriptive statistics, histograms, boxplot)
3. Relationships (correlation matrix, heatmap, scatterplots)
4. Regression modelling (simple model with BMI; multiple model with BMI, blood pressure and s5)
5. Model evaluation (residuals plot, VIF, confidence intervals)

## Key results

- BMI (r = 0.59) and s5 (r = 0.57) are most strongly related to progression.
- Simple model: each extra unit of BMI is associated with about 10 units more progression (R² = 0.34).
- Multiple model (BMI, blood pressure, s5): all three are significant and together explain about 48% of the variation.
- No multicollinearity problem (VIF 1.27 to 1.35) and no serious problems in the residuals plot.

## Interpretation and limitations

The data are observational, so the results show associations, not causes. Important information such as medication, diet and physical activity is missing. About half of the variation remains unexplained, so the model is not accurate enough to predict progression for individual patients.

## Files

| File | Description |
|---|---|
| [Diabetes_Analysis.R](Diabetes_Analysis.R) | R script with the full analysis |
| [diabetes.tab.txt](diabetes.tab.txt) | Dataset used in the analysis |
| [Diabetes_Report.pdf](Diabetes_Report.pdf) | Analytical report answering the six project questions |
| [Diabetes_Presentation.pdf](Diabetes_Presentation.pdf) | Short presentation for a non-specialist decision-maker |
| [Figures](Figures) | Figures used in the report |

To run the analysis, place the R script and the dataset in the same folder, open the script in RStudio, set the working directory to the source file location, and run the script from top to bottom.

## Reflection

This project helped me understand the full workflow of a data analysis, from checking the data to building and evaluating regression models. The most difficult parts were the technical setup in R (file paths, packages and errors) and learning to interpret the results correctly, especially the difference between statistical significance and practical importance. With more time, I would test the model on new data and explore other combinations of predictors.
