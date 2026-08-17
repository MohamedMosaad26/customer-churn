🏦 Bank Customer Churn Prediction
A machine learning project that predicts whether a bank customer is likely to **churn (leave)** or **stay**, using customer demographic, financial, and account-related data.

The project follows an end-to-end **Data Science & Machine Learning pipeline**, including data exploration, preprocessing, feature engineering, handling class imbalance, model training, evaluation, and an interactive prediction application built with **Gradio**.

---

## 📌 Project Overview

Customer churn is a major challenge in the banking industry. Identifying customers who are likely to leave allows banks to take proactive retention actions and reduce customer loss.

This project aims to build a machine learning classification system that can:

* Identify customers at risk of churning
* Analyze the factors associated with customer churn
* Compare multiple machine learning models
* Predict churn probability for individual customers
* Categorize customers into different risk levels
* Provide an interactive interface for real-time predictions

### 🎯 Target Variable

`Exited`

* `1` → Customer churned
* `0` → Customer stayed

---

## 📂 Project Structure

```text
bank-churn-prediction/
│
├── customer_churn.ipynb       # Main notebook: EDA → preprocessing → ML
├── churn_gui.py               # Gradio interactive prediction application
├── Churn_Modelling.csv        # Dataset
├── requirements.txt           # Python dependencies
└── README.md                  # Project documentation
```

---

## 📊 Dataset

The project uses the **Churn Modelling Dataset**, which contains information about bank customers and whether they exited the bank.

### Main Features

| Feature           | Description                              |
| ----------------- | ---------------------------------------- |
| `CreditScore`     | Customer's credit score                  |
| `Geography`       | Customer's country                       |
| `Gender`          | Customer's gender                        |
| `Age`             | Customer's age                           |
| `Tenure`          | Number of years as a bank customer       |
| `Balance`         | Customer's account balance               |
| `NumOfProducts`   | Number of bank products used             |
| `HasCrCard`       | Whether the customer owns a credit card  |
| `IsActiveMember`  | Whether the customer is an active member |
| `EstimatedSalary` | Estimated annual salary                  |
| `Exited`          | Target variable indicating churn         |

### Dataset Source

[Kaggle — Churn Modelling Dataset](https://www.kaggle.com/datasets/shrutimechlearn/churn-modelling)

---

# 🔍 Machine Learning Pipeline

## 1. Exploratory Data Analysis

The dataset was explored to understand customer behavior and identify patterns associated with churn.

The analysis included:

* Univariate analysis
* Bivariate analysis
* Churn distribution analysis
* Churn rate by geography
* Churn rate by gender
* Gender × geography analysis
* Correlation analysis
* Age distribution analysis
* KDE plots comparing churners and non-churners

---

## 2. Feature Engineering

Additional features were created to provide the models with more meaningful information.

| Feature             | Description                                                   |
| ------------------- | ------------------------------------------------------------- |
| `HasBalance`        | Indicates whether the customer has a positive account balance |
| `BalancePerProduct` | Account balance divided by number of products                 |
| `AgeGroup`          | Customer age grouped into meaningful categories               |

These engineered features help capture relationships that may not be directly represented by the original variables.

---

## 3. Data Preprocessing

The following preprocessing steps were applied:

* Removed irrelevant identifiers:

  * `RowNumber`
  * `CustomerId`
  * `Surname`
* Handled categorical variables using **One-Hot Encoding**
* Encoded:

  * `Geography`
  * `Gender`
  * `AgeGroup`
* Applied **SMOTE** to address class imbalance
* Scaled numerical features using **StandardScaler**
* Split the data into training and testing sets

---

## 🤖 Machine Learning Models

Three classification models were trained and compared:

| Model                   | Description                                  |
| ----------------------- | -------------------------------------------- |
| **Logistic Regression** | Baseline linear classification model         |
| **Random Forest**       | Ensemble model using multiple decision trees |
| **Gradient Boosting**   | Boosting-based ensemble model                |

### Model Configuration

* **Random Forest**

  * 500 trees
  * Maximum depth: 20

* **Gradient Boosting**

  * 100 estimators

---

## 📈 Model Evaluation

The models were evaluated using multiple classification metrics:

* **Accuracy**
* **F1 Score**
* **ROC-AUC**

| Model               | Accuracy | F1 Score | ROC-AUC |
| ------------------- | -------: | -------: | ------: |
| Logistic Regression |        — |        — |       — |
| Random Forest       |        — |        — |       — |
| Gradient Boosting   |        — |        — |       — |

> Replace the values above with the actual results generated by the notebook.

### Why F1 Score?

Because customer churn datasets are often imbalanced, **F1 Score** provides a better view of the model's ability to balance precision and recall than accuracy alone.



# 🖥️ Interactive Prediction Application

The project includes an interactive prediction interface built using **Gradio**.

The application allows users to enter customer information and receive:

* ✅ Churn / Stay prediction
* ⚠️ Customer risk level
* 📊 Churn probability
* 📊 Stay probability
* 📈 Model performance metrics

### Risk Levels

The application categorizes customers into:

* 🔴 **High Risk**
* 🟡 **Medium Risk**
* 🟢 **Low Risk**

---

## ▶️ Run the Application

After installing the required dependencies, run:

```bash
python churn_gui.py
```

The Gradio application will be available locally at:

```text
http://localhost:7860
```

Open the address in your browser to interact with the model.

---

# ⚙️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/MohamedMosaad26/bank-churn-prediction.git
```

### 2. Navigate to the Project

```bash
cd bank-churn-prediction
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Notebook

```bash
jupyter notebook customer_churn.ipynb
```

### 5. Run the Gradio Application

```bash
python churn_gui.py
```

---

# 📦 Technologies & Libraries

The project was developed using:

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Scikit-learn**
* **Imbalanced-learn / SMOTE**
* **Gradio**
* **Jupyter Notebook**

---

# 🧠 Key Findings

The exploratory analysis revealed several important patterns:

* **Age** is one of the strongest factors associated with customer churn.
* Customers in **Germany** show a higher churn rate compared with customers in France and Spain.
* **Inactive members** represent a higher-risk customer segment.
* Customers with certain combinations of **age, balance, and product usage** show increased churn risk.
* Customer engagement and account characteristics can provide valuable signals for identifying potential churn.

> These findings are based on exploratory analysis of the dataset and should not be interpreted as causal relationships.

---

# 🚀 Future Improvements

* [ ] Add **SHAP** for model explainability
* [ ] Perform hyperparameter tuning using `GridSearchCV` or `RandomizedSearchCV`
* [ ] Add confusion matrix visualization
* [ ] Add ROC curve visualization
* [ ] Improve the Gradio interface
* [ ] Add model explainability to individual predictions
* [ ] Deploy the application to **Hugging Face Spaces**
* [ ] Add automated model retraining pipeline

---

# 👤 Author

## Mohamed Mosaad

**Data Science Student | Machine Learning Enthusiast**

Interested in building data-driven solutions using **Python, Machine Learning, Data Analysis, and AI**.

* GitHub: [@MohamedMosaad26](https://github.com/MohamedMosaad26)
* LinkedIn: [Mohamed Mosaad](https://www.linkedin.com/)

---

# 📄 License

This project is open source and available under the **MIT License**.



 
 
