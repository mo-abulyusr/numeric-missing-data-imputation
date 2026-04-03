# Missing Data Imputation Tutorial

This repo shows a simple comparison of two ways to fill in missing values in a continuous numeric variable: basic imputation with mean or median, and a more context-aware approach with KNN.

The example uses the `Insulin` column from the diabetes dataset. That column has a large amount of missing data, so it is a good test case for seeing how different imputation methods behave.

## What This Covers

The goal is to answer a simple question: when a numeric variable has a lot of missing values, what happens if we fill the gaps with a quick average versus a method that looks at similar rows in the dataset?

This tutorial walks through:

1. The dataset and the missing-value problem
2. Why `Insulin` is the target variable
3. How mean and median imputation behave
4. How KNN imputation works
5. What changes in the data after each method

## How It Works

The notebook compares the methods in a clear sequence:

1. Load the diabetes dataset
2. Review the missing-value pattern
3. Apply simple imputation with mean and median
4. Apply KNN imputation using the rest of the dataset as context
5. Compare the results and look at how well each method preserves the original structure of the data

The main takeaway is simple: mean and median are fast, but they can flatten the shape of the data. KNN takes more work, but it usually gives a more realistic result when missingness is substantial.

## What’s In The Repo

- [`notebooks/diabetes_missing_data_imputation.ipynb`](notebooks/diabetes_missing_data_imputation.ipynb) - main tutorial notebook
- [`data/diabetes_data.csv`](data/diabetes_data.csv) - source dataset used in the tutorial
- [`reports/df_profile.html`](reports/df_profile.html) - exploratory data profile for a quick scan of the dataset
- [`reports/imputing_continuous_numeric_variables.pdf`](reports/imputing_continuous_numeric_variables.pdf) - written summary of the analysis
- [`references/DataDictionary.pdf`](references/DataDictionary.pdf) - variable reference for the dataset

## How To Use It

Start with the notebook in `notebooks/`.

If you want the shortest path, read `reports/imputing_continuous_numeric_variables.pdf` first. It gives the summary in a compact form.

If you want more context on the raw data, open `reports/df_profile.html` and `references/DataDictionary.pdf`.

## File Layout

```text
data/
  diabetes_data.csv
notebooks/
  diabetes_missing_data_imputation.ipynb
reports/
  df_profile.html
  imputing_continuous_numeric_variables.pdf
references/
  DataDictionary.pdf
```

## Notes

- The notebook now reads the dataset from `../data/diabetes_data.csv`.
- The notebook writes the profile report to `../reports/df_profile.html`.
- The repo keeps the root clean so the first thing you see is the guide, not the files.
