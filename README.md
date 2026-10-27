# 🌐 Phishing URL Detection Using Decision Tree

## 📌 Project Overview

This project focuses on detecting phishing URLs using Machine Learning. A **Decision Tree Classifier** is trained to classify websites as **Phishing** or **Legitimate** based on URL characteristics and website-related features.

The project uses the **PhiUSIIL Phishing URL Dataset** to train and evaluate the model. Its performance is assessed using Accuracy, Precision, Recall, F1-Score, and Specificity. Visualizations, including a Confusion Matrix and Decision Tree Plot, help interpret the model's predictions.

## 🎯 Objectives

The main objectives of this project are to:

- Detect phishing URLs using Machine Learning.
- Analyze URL and website features to identify suspicious websites.
- Train a Decision Tree classification model.
- Evaluate model performance using standard classification metrics.
- Visualize the decision-making structure of the model.
- Analyze classification results using a Confusion Matrix.

## 📂 Dataset Information

**Dataset Name:** PhiUSIIL Phishing URL Dataset

The dataset contains URL information, domain characteristics, security indicators, and website content features that can help distinguish phishing websites from legitimate ones.

### Dataset Details

| Attribute | Description |
|---|---|
| Total Records | 78,962 |
| Total Columns | 56 |
| Numerical Features Selected | 50 |
| Target Column | `label` |
| Missing Values | 45 |

### Target Labels

The target labels are converted into binary values during preprocessing.

**Original Labels:**
- `0` — Phishing
- `1` — Legitimate

**After Preprocessing:**
- `0` — Legitimate
- `1` — Phishing

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Google Colab / Jupyter Notebook

## ⚙️ Project Workflow

### 1. Data Loading and Exploration

Load the dataset using Pandas and examine its structure, first five rows, column names, missing values, and target class distribution.

### 2. Data Preprocessing

The following preprocessing steps are performed:

- Remove records with missing target labels.
- Convert the original target labels into binary values.
- Select numerical features for model training.
- Replace infinite values with missing values.
- Handle missing numerical values using column medians.

### 3. Train-Test Split

Split the dataset into training and testing sets to evaluate the model's performance on unseen records.

- **Training Set:** 80%
- **Testing Set:** 20%
- **Random State:** 42
- **Stratified Sampling:** Maintains the class distribution across both sets.

### 4. Model Training

A Decision Tree Classifier is trained using the following parameters:

```python
DecisionTreeClassifier(
    max_depth=5,
    class_weight="balanced",
    random_state=42
)
```

The model learns patterns in the selected URL and website features to classify websites as phishing or legitimate.

### 5. Model Prediction

The trained model predicts the target labels for the test dataset. The predicted labels are compared with the actual labels to evaluate classification performance.

### 6. Model Evaluation

The model is evaluated using the following metrics:

- **Accuracy:** Measures the proportion of correctly classified records.
- **Precision:** Measures the proportion of predicted positive cases that are correct.
- **Recall:** Measures the proportion of actual positive cases correctly identified.
- **F1-Score:** Represents the harmonic mean of precision and recall.
- **Specificity:** Measures the proportion of actual negative cases correctly identified.

### 7. Data Visualization

The project generates the following visualizations:

- **Decision Tree Plot:** Illustrates the model's decision-making structure.
- **Confusion Matrix:** Displays the number of correct and incorrect predictions for each class.

## 📊 Model Evaluation Results

The initial experiment produced the following evaluation results:

| Metric | Score |
|---|---:|
| Accuracy | 1.0000 (100%) |
| Precision | 1.0000 (100%) |
| Recall | 1.0000 (100%) |
| F1-Score | 1.0000 (100%) |
| Specificity | 1.0000 (100%) |

### Confusion Matrix

| Actual Class | Predicted Legitimate | Predicted Phishing |
|---|---:|---:|
| Legitimate | 9,184 | 0 |
| Phishing | 0 | 6,609 |

**Note:** These results represent the initial experiment. Perfect scores are unusual in real-world phishing detection. Further validation is necessary to check for data leakage, duplicate records, overlapping features, or other issues before concluding that the model generalizes perfectly to unseen URLs.

## 📈 Key Findings

- The Decision Tree Classifier was trained using the selected numerical features.
- The model correctly classified all test records in the initial experiment.
- The Confusion Matrix showed zero false positives and zero false negatives.
- All reported evaluation metrics reached 100% in the initial experiment.
- Additional testing is required to verify performance on independent datasets and previously unseen URLs.

## 🚀 How to Run the Project

Follow these steps to run the project:

1. Download or clone the project repository.
2. Open the notebook in Google Colab or Jupyter Notebook.
3. Upload the PhiUSIIL Phishing URL Dataset CSV file.
4. Update the dataset path if necessary.
5. Install the required libraries.
6. Run all notebook cells in sequence.
7. Review the evaluation metrics and visualizations.

### Required Libraries

Install the required Python libraries using the following command:

```bash
pip install pandas numpy matplotlib scikit-learn
```

## 🔮 Future Enhancements

Future improvements may include:

- Evaluating the model using cross-validation.
- Checking for duplicate URLs and potential data leakage.
- Testing the model on an independent dataset.
- Comparing Decision Tree performance with Random Forest and other classification algorithms.
- Developing a simple web application for URL classification.
- Improving model reliability when detecting previously unseen phishing URLs.

## 🏁 Conclusion

This project demonstrates the application of Machine Learning to phishing URL detection using a Decision Tree Classifier. By analyzing URL and website-related features, the model classifies websites as phishing or legitimate.

The Confusion Matrix and classification metrics provide insights into the model's performance. However, independent testing and further validation are essential before deploying the model in a real-world security application.
