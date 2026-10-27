# Alibi Loan Approval Explainable AI

## Project Overview

This project develops a machine learning model to predict loan approval outcomes and uses Explainable AI (XAI) techniques to interpret individual predictions.

## Objectives

- Train a Random Forest classifier on a loan approval dataset.
- Evaluate performance using accuracy, precision, recall, F1-score and ROC-AUC.
- Use Alibi's AnchorTabular explainer to generate local rule-based explanations.
- Visualize model evaluation results and investigate candidate alternative applicant records.

## Technologies Used

- Python
- Pandas and NumPy
- Scikit-learn
- Alibi
- Matplotlib

## Dataset

Loan Approval Prediction Dataset by Archit Sharma, available on Kaggle:

https://www.kaggle.com/datasets/architsharma01/loan-approval-prediction-dataset

Download the dataset from Kaggle and place the CSV file where the Python script can locate it. Follow the dataset's licensing and usage conditions.

## Installation

Install the required libraries:

```bash
pip install -r requirements.txt
```

## Running the Project

Run the script from a terminal:

```bash
python alibi_loan_approval.py
```

For inline graphs in Google Colab, upload the script and dataset, install the requirements, and run:

```python
%run alibi_loan_approval.py
```

## Model Evaluation

Report the measured test-set metrics from your actual run:

- Accuracy: 97.89%
- Precision (Approved): 98.49%
- Recall (Approved): 98.12%
- F1-score (Approved): 98.30%
- ROC-AUC: 0.9988

## Explainability

Alibi's AnchorTabular explainer generates rule-based explanations for individual model predictions. The project also includes a custom Python method for exploring candidate alternative applicant records.

## Limitations and Ethical Use

This is an educational project, not a real lending decision system. High test-set performance does not guarantee generalization, fairness, or causal validity. Candidate alternatives are model-based explorations, not guaranteed routes to loan approval.

## Author

Add your name, course and institution here.
