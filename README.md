# Machine learning based macthing analysis 

Matching is a technique often used to balance datasets or control for confounding variables, especially in causal inference

This code script is aim at achieving the following objectives:

1. Learn to apply machine learning algorithms for matching analysis.
2. Develop skills in preprocessing and feature engineering for matching.
3. Assess the quality of matches using statistical and visual methods.
4. Interpret and report findings from a matching analysis.


# Dataset

The [Can Path Student Dataset](https://canpath.ca/student-dataset/) was used  to perform a maatching analysis. The dataset has already been cleaned using [Multivariate Imputation by Chained Equations](https://www.rdocumentation.org/packages/mice/versions/3.17.0/topics/mice) method to handle missing data. 

The data has 41187 observation and 93 columns after cleaning. 

# Description of Project

This R script performs a matching analysis to investigate the causal association between hypertension and diabetes mellitus using the can_path_student dataset. It begins by loading necessary libraries, importing the dataset, and converting categorical variables into factors. The diabetes and hypertension variables are recoded for clarity.

A crude measure of association is first examined using contingency tables and a chi-square test, followed by an odds ratio calculation via the epitools package. A logistic regression model is then fitted to estimate the association between hypertension and diabetes before adjusting for potential confounders.

Matching techniques are applied to balance the covariates. First, nearest-neighbor (1:1 NN) matching is performed using MatchIt, and balance diagnostics are assessed with standardized mean differences, histograms, and love plots. Next, generalized full matching is applied as an alternative, demonstrating better balance. The best matching method is selected based on standardized mean differences.

The treatment effect is estimated using a weighted generalized estimating equation (GEE) regression on the matched sample. Additionally, inverse probability of treatment weighting (IPTW) is employed to estimate the treatment effect without direct matching. Finally, the results from all models (crude, adjusted, matched, and IPTW) are compared to assess the robustness of findings.

# Files in the repository 

1. The [R Markdown](https://github.com/Bernard-AI4PH/Matching_in_epi/blob/main/Bernard_Asante_CHEP898_Matching.Rmd) file contains the complete analysis for investigating the causal association between hypertension and diabetes using matching techniques. It includes data preprocessing, contingency tables, logistic regression, matching methods (nearest-neighbor and full matching), and inverse probability of treatment weighting (IPTW) to estimate treatment effects.

2. This [HTML file](https://github.com/Bernard-AI4PH/Matching_in_epi/blob/main/Bernard_Asante_CHEP898_Matching.html) is the rendered output of the [R Markdown](https://github.com/Bernard-AI4PH/Matching_in_epi/blob/main/Bernard_Asante_CHEP898_Matching.Rmd) file. It presents the full analysis, including tables, figures, and statistical results, in a structured and interactive format for easy interpretation of findings.


