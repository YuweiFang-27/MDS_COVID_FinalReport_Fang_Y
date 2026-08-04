# MDS_COVID_FinalReport_Fang_Y

This repository contains the code, processed data and analysis results used for my Data Science Research Project Part B final report.

## Project title

**Exploring the willingness and perceived feasibility of self-isolation among Chinese residents during COVID-19**

The study separately modelled willingness to self-isolate and perceived feasibility of self-isolation using Logistic Regression and Random Forest. Model performance and Random Forest feature importance were then compared between the two outcomes.

## Repository structure

```text
MDS_COVID_FinalReport_Fang_Y/
│
├── code/
│   ├── 000_china_comparison.ipynb
│   ├── 00_missingvalue_check.ipynb
│   ├── 0_variable_definition.ipynb
│   ├── 1_outcome_processing.ipynb
│   ├── 2_predictor_processing.ipynb
│   ├── 3_final_processing.ipynb
│   ├── 4_split_data.ipynb
│   ├── 5_prepare_models.ipynb
│   ├── 6_logistic_regression.ipynb
│   ├── 7_random_forest.ipynb
│   └── 8_feature_importance.ipynb
│
├── data/
│   ├── raw/
│   ├── data_processed/
│   └── model_inputs/
│
├── results/
│   ├── rf_feature_importance_plots/
│   ├── model cross-validation results
│   └── independent test results
│
├── Report_Fang_Y.Rmd
├── Report_Fang_Y.pdf
└── README.md
```

## Code files

The main notebooks should be run in numerical order.

- `000_china_comparison.ipynb`: Conducts the preliminary comparison of self-isolation willingness and perceived feasibility in the China and Australia samples and generates row-percentage heatmaps.

- `00_missingvalue_check.ipynb`: Checks missing values in the raw China survey data and identifies variables with less than 10% missingness.

- `0_variable_definition.ipynb`: Selects and organises the original outcome and predictor variables used in the analysis.

- `1_outcome_processing.ipynb`: Recodes the original perceived-feasibility and willingness responses into binary outcome variables.

- `2_predictor_processing.ipynb`: Recodes and constructs the demographic, household, employment, protective behaviour, contact, testing, health and survey-wave predictors.

- `3_final_processing.ipynb`: Selects the final analysis variables, applies complete-case filtering, converts categorical predictors into dummy variables and creates the model-ready dataset.

- `4_split_data.ipynb`: Uses joint stratification to divide the model-ready data into training and independent test sets using an 80:20 ratio.

- `5_prepare_models.ipynb`: Creates the common predictor matrices and separate outcome vectors used for the two modelling tasks.

- `6_logistic_regression.ipynb`: Tunes, fits and evaluates the Logistic Regression models using five-fold stratified cross-validation and independent test data.

- `7_random_forest.ipynb`: Conducts Random Forest hyperparameter tuning, cross-validation and independent test-set evaluation for both outcomes.

- `8_feature_importance.ipynb`: Repeats the selected Random Forest models 100 times and produces the variable-level feature importance comparison and difference plots.

## Data files

- `data/raw/`: Contains the original China survey data from the Imperial College London YouGov COVID-19 Behaviour Tracker.

- `data/data_processed/`: Contains the datasets created during variable processing, complete-case filtering and the training-test split.

- `data/model_inputs/`: Contains the training and test predictor matrices and the separate outcome vectors used for model fitting.

## Result files

- `rf_feasibility_cv_summary.csv` and `rf_willingness_cv_summary.csv` contain the five-fold cross-validation performance and selected Random Forest settings for the two outcomes.

- `rf_feasibility_test_summary.csv` and `rf_willingness_test_summary.csv` contain the independent test-set performance of the selected Random Forest models.

- `.joblib` files store the detailed Random Forest cross-validation and independent test results for perceived feasibility and willingness.

- `rf_willingness_test_results.zip` contains the compressed willingness test-result file.

- `china_australia_feasibility_willingness.png` contains the preliminary row-percentage heatmaps for the China and Australia samples.

- `results/rf_feature_importance_plots/` contains the variable-level feature importance tables, the union of the two Top-10 lists, the importance-difference results and the final comparison figures.

## Analysis workflow

The analysis was conducted in Python, with the code organised and executed in Jupyter Notebook.

The main workflow was:

1. select and process the outcome and predictor variables;
2. create the complete-case and model-ready datasets;
3. divide the data into training and independent test sets;
4. fit and compare Logistic Regression and Random Forest;
5. evaluate model performance using cross-validation and independent test data;
6. compare Random Forest feature importance between perceived feasibility and willingness.

## Data source

The survey data were obtained from the **Imperial College London YouGov COVID-19 Behaviour Tracker**. This project used the China sample collected across repeated survey waves from April to September 2020.

Jones, Sarah P., Imperial College London Big Data Analytical Unit, and YouGov Plc. 2020. *Imperial College London YouGov COVID-19 Data Hub.* Version 1.0. YouGov Plc. https: //github.com/YouGov-Data/covid-19-tracker.

## Acknowledgement

The methodological preparation for this project were developed with reference to Ryan et al. (2025):

Ryan, Matthew, Jinjing Ye, Justin Sexton, Roslyn I. Hickson, and Emily Brindal. 2025. “Face Mask Mandates Alter Major Determinants of Adherence to Protective Health Behaviours in Australia.” *Royal Society Open Science* 12 (3): 241941. https://doi.org/10.1098/rsos.241941.
