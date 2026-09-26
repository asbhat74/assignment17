# Practical Application III: Comparing Classifiers

## Overview

This project compares the performance of four machine learning classifiers on a binary classification task: predicting whether a customer will subscribe to a term deposit at a Portuguese banking institution.

**Classifiers Evaluated:**
- K-Nearest Neighbors (KNN)
- Logistic Regression
- Decision Trees
- Support Vector Machines (SVM)

## Business Objective

Predict whether a customer will subscribe to a term deposit based on their personal information and previous marketing campaign data. This enables targeted marketing efforts to identify customers most likely to subscribe.

## Dataset

**Source:** [UCI Machine Learning Repository - Bank Marketing](https://archive.ics.uci.edu/ml/datasets/bank+marketing)

**Description:** Results from direct marketing campaigns of a Portuguese banking institution. Multiple campaigns were conducted with 41,188 customer records.

**Key Details:**
- **Records:** 41,188 customer interactions
- **Input Features:** 20 (demographic, economic, and campaign-related)
- **Target Variable:** Binary ('yes' = subscribed to term deposit, 'no' = did not subscribe)
- **Missing Values:** None
- **Data Types:** 5 float, 5 integer, 11 string (categorical) features

### Feature Categories

**Bank Client Data:**
- age, job, marital status, education, default status, housing loan, personal loan

**Contact Information:**
- contact type (cellular/telephone)
- month, day of week, duration of last contact

**Campaign Data:**
- number of contacts in current campaign
- days since previous contact
- number of previous contacts
- outcome of previous campaign

**Economic Context:**
- employment variation rate
- consumer price index
- consumer confidence index
- euribor 3-month rate
- number of employees

## Project Structure

```
module17_starter/
├── README.md                      # This file
├── Requirements.md                # Assignment rubric (formatted table)
├── prompt_III.ipynb              # Jupyter notebook with analysis and implementation
├── CRISP-DM-BANK.pdf             # Reference paper: Materials and Methods
└── data/
    ├── bank-additional-full.csv   # Complete dataset (41,188 records)
    ├── bank-additional.csv        # Alternative dataset version
    └── bank-additional-names.txt  # Feature names reference
```

## Notebook Contents

The `prompt_III.ipynb` notebook is structured around the following problems:

1. **Problem 1:** Understanding the Data
   - Read reference materials to understand dataset context
   - Identify number of marketing campaigns represented

2. **Problem 2:** Read in the Data
   - Load CSV file into pandas DataFrame

3. **Problem 3:** Understanding the Features
   - Analyze missing values and data types
   - Identify features requiring encoding
   - Summary: No missing values; categorical features need encoding

4. **Problem 4:** Understanding the Task
   - State the business objective clearly
   - Identify key insights and context

5. **Problem 5:** Engineering Features
   - Encode categorical variables
   - Prepare features and target for modeling

6. **Problem 6:** Train/Test Split
   - Split data into training and test sets

7. **Problem 7:** A Baseline Model
   - Establish baseline performance metric

8. **Problem 8:** A Simple Model
   - Build initial Logistic Regression model

9. **Problem 9:** Score the Model
   - Evaluate accuracy

10. **Problem 10:** Model Comparisons
    - Compare KNN, Logistic Regression, Decision Trees, and SVM
    - Present findings in comparative table

11. **Problem 11:** Improving the Model
    - Hyperparameter tuning
    - Grid search optimization

## Key Findings

### Data Quality
- ✓ Complete dataset with zero missing values
- ✓ Proper data types for numeric features
- ✓ Well-balanced feature set (20 inputs + 1 target)
- ⚠️ Note: `duration` feature known only after call completion (excluded from realistic models)

### Categorical Features
| Feature | Unique Values | Type |
|---------|---------------|------|
| job | 12 | Nominal |
| marital | 4 | Nominal |
| education | 8 | Ordinal |
| default, housing, loan | 3 each | Binary + unknown |
| contact | 2 | Binary |
| month | 10 | Ordinal |
| day_of_week | 5 | Ordinal |
| poutcome | 3 | Nominal |
| y (target) | 2 | Binary |

## Requirements

- Python 3.x
- pandas
- scikit-learn
- numpy
- matplotlib or seaborn (for visualization)

## Getting Started

1. Open `prompt_III.ipynb` in Jupyter Notebook
2. Follow problems 1-11 sequentially
3. Run code cells to analyze data and train models
4. Compare classifier performance using the summary table

## References

- UCI Machine Learning Repository: [Bank Marketing Dataset](https://archive.ics.uci.edu/ml/datasets/bank+marketing)
- CRISP-DM: [Paper included in project](CRISP-DM-BANK.pdf)

## Assignment Rubric

See [Requirements.md](Requirements.md) for detailed grading criteria covering:
- Project organization
- Syntax and code quality
- Visualizations
- Modeling approach
- Findings and interpretation
