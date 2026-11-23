# Telco Customer Churn Prediction

A supervised machine-learning project that predicts whether a telecom customer is likely to leave the service (`Churn = Yes`). The notebook compares four classification algorithms:

- K-Nearest Neighbours (KNN)
- Gaussian Naive Bayes
- Support Vector Machine (SVM)
- Decision Tree

The project uses the IBM Telco Customer Churn benchmark dataset and explores customer behaviour, preprocessing, class imbalance, model evaluation, and business interpretation.

## Project structure

```text
telco-churn-supervised-learning/
├── CustomerChurn_SupervisedLearning.ipynb
├── README.md
├── requirements.txt
├── summary_report.md
├── .gitignore
└── data/
    └── README.md
```

> The notebook is the main implementation. No additional Python script (`.py`) is required or included.

## Dataset

Download the **IBM Telco Customer Churn** dataset from Kaggle:

https://www.kaggle.com/datasets/blastchar/telco-customer-churn

Place the CSV file in the `data/` folder and name it:

`WA_Fn-UseC_-Telco-Customer-Churn.csv`

The notebook currently loads the CSV using:

```python
pd.read_csv('WA_Fn-UseC_-Telco-Customer-Churn.csv')
```

Therefore, either:
1. Start Jupyter from the `data/` folder when running the notebook, **or**
2. Change the notebook's CSV path to `data/WA_Fn-UseC_-Telco-Customer-Churn.csv`.

No dataset is bundled because it was not included with the uploaded files.

## Requirements

Python 3.9 or later is recommended. Install the libraries with:

```bash
pip install -r requirements.txt
```

If you use Jupyter Notebook:

```bash
jupyter notebook
```

Open `CustomerChurn_SupervisedLearning.ipynb` and run the cells from top to bottom after placing the dataset at the expected path.

## Notebook workflow

1. Load and inspect the dataset.
2. Perform exploratory data analysis.
3. Clean and prepare the data; engineer features and encode categories.
4. Split the data into training and test sets.
5. Scale numerical features and apply SMOTE to training data only.
6. Train and evaluate KNN, Gaussian Naive Bayes, SVM, and Decision Tree.
7. Compare model metrics and ROC curves.
8. Compare SMOTE with balanced class weights.
9. Perform basic false-negative analysis.
10. Save the trained Decision Tree model as `churn_model.pkl`.

## Evaluation focus

The project reports Accuracy, Precision, Recall, F1-score, and ROC-AUC. Recall for the churn class is particularly important because a false negative represents a customer who leaves but was not flagged by the model. Precision also matters because the retention team has limited capacity to contact flagged customers.

## Important notes

- Keep the test set untouched by SMOTE; oversampling belongs on training data only.
- The notebook's saved `churn_model.pkl` is the Decision Tree estimator trained on scaled features. It is **not** a complete preprocessing pipeline. For predictions on new raw customer records, the same preprocessing and scaling steps must be applied first.
- Model results and business conclusions should be filled in after executing the notebook. Do not report unverified metrics.

## Suggested GitHub repository

`telco-churn-supervised-learning`

Upload the notebook and supporting files in this project folder. Add the generated `churn_model.pkl` only after running the notebook if you want to include the trained model artifact.
