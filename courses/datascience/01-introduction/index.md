# Data Science Careers, Process, and Jupyter Notebook

This section explains the major **data-related career roles**, the **Data Science workflow**, and how to use **Jupyter Notebook**, which is the primary development environment used in data science.

---

# 1. Data Science Career Profiles

## 1. Data Analyst

### Role
A Data Analyst focuses on analyzing historical data to extract insights and help businesses make informed decisions.

### Key Responsibilities

- Collect and clean data
- Perform exploratory data analysis (EDA)
- Create dashboards and reports
- Identify trends and patterns
- Communicate insights to business stakeholders

### Technical Skills

- Python / R
- SQL
- Excel
- Data Visualization tools
  - Tableau
  - Power BI
- Pandas
- Matplotlib / Seaborn
- Statistics basics

---

## 2. Data Engineer

### Role
A Data Engineer builds and maintains the **data infrastructure and pipelines** required for analytics and machine learning.

### Key Responsibilities

- Design data pipelines
- Build ETL/ELT workflows
- Manage data lakes and warehouses
- Ensure data quality and reliability
- Optimize data storage and processing

### Technical Skills

- Python / Scala / Java
- SQL
- Apache Spark
- Apache Kafka
- Hadoop
- Airflow
- Data Warehouses
  - Snowflake
  - Redshift
  - BigQuery
- Cloud Platforms
  - AWS
  - Azure
  - GCP

---

## 3. Data Scientist

### Role
A Data Scientist analyzes large datasets and builds predictive models using machine learning.

### Key Responsibilities

- Data exploration
- Feature engineering
- Model building
- Model evaluation
- Communicate insights through visualization
- Build predictive systems

### Technical Skills

- Python
- Pandas
- NumPy
- Scikit-Learn
- Statistics
- Machine Learning algorithms
- Data visualization
- SQL
- Jupyter Notebook

---

## 4. Machine Learning Engineer

### Role
A Machine Learning Engineer focuses on **deploying, scaling, and maintaining machine learning models in production environments**.

### Key Responsibilities

- Deploy ML models
- Build ML pipelines
- Optimize model performance
- Integrate models with applications
- Monitor model performance

### Technical Skills

- Python
- TensorFlow / PyTorch
- Docker
- Kubernetes
- ML pipelines
- MLOps tools
  - MLflow
  - Kubeflow
  - Airflow
- Cloud ML services

---

## 5. AI Engineer

### Role
AI Engineers build systems that simulate human intelligence such as **chatbots, recommendation systems, computer vision, and generative AI applications**.

### Key Responsibilities

- Build AI applications
- Implement deep learning models
- Work with NLP and computer vision
- Integrate AI APIs
- Deploy AI services

### Technical Skills

- Python
- Deep Learning frameworks
  - TensorFlow
  - PyTorch
- NLP libraries
  - NLTK
  - spaCy
- Computer Vision
  - OpenCV
- Generative AI tools
- Cloud AI services

---

# 2. Data Science Process

The Data Science process is a structured workflow used to extract insights from data and build predictive models.

## Step 1: Problem Understanding

Understand the business problem and define objectives.

Example:
Predict customer churn.

---

## Step 2: Data Collection

Gather data from multiple sources:

- Databases
- APIs
- CSV files
- Web scraping
- Sensors

---

## Step 3: Data Cleaning

Prepare data by removing errors.

Common tasks:

- Handle missing values
- Remove duplicates
- Fix inconsistent data
- Handle outliers

---

## Step 4: Exploratory Data Analysis (EDA)

Understand the data using statistics and visualization.

Techniques:

- Correlation analysis
- Distribution analysis
- Visualization plots

---

## Step 5: Feature Engineering

Transform raw data into useful features.

Examples:

- Encoding categorical variables
- Scaling numeric features
- Creating new derived features

---

## Step 6: Model Building

Train machine learning models.

Examples:

- Linear Regression
- Logistic Regression
- Random Forest
- KNN
- Decision Tree

---

## Step 7: Model Evaluation

Evaluate performance using metrics.

Examples:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

---

## Step 8: Model Deployment

Deploy models into production environments.

Deployment options:

- REST APIs
- Cloud services
- Batch pipelines

---

## Step 9: Monitoring and Maintenance

Monitor model performance in production.

Tasks:

- Detect model drift
- Retrain models
- Monitor prediction accuracy

---

# 3. Jupyter Notebook

Jupyter Notebook is an interactive environment used by data scientists to write code, visualize data, and document analysis.

---

# 4. Jupyter Notebook Platforms

## 1. Anaconda (Local)

A popular distribution that includes Python and data science libraries.

Features:

- Local development
- Preinstalled packages
- Easy environment management

---

## 2. Google Colab

A cloud-based notebook environment provided by Google.

Features:

- Free GPU access
- No installation required
- Easy sharing

---

## 3. AWS SageMaker

A managed machine learning platform from AWS.

Features:

- Notebook environment
- Model training
- Model deployment

---

## 4. Kaggle Notebooks

An online environment for data science experiments.

Features:

- Free datasets
- GPU/TPU support
- Collaboration

---

# 5. Installing Jupyter Notebook Locally

## Install using pip

```bash
pip install notebook
```

## Start Jupyter

```bash
jupyter notebook
```

---

## Install using Anaconda

Download Anaconda:

https://www.anaconda.com

Launch Jupyter:

```
Anaconda Navigator → Launch Jupyter Notebook
```

---

## 6. Jupyter Notebook Interface

Main components:

- Notebook dashboard  
- Code cells  
- Markdown cells  
- Kernel (Python runtime)

---

## 7. Useful Jupyter Commands

### Create New Notebook

```
New → Python 3
```

### Run a Cell

```
Shift + Enter
```

### Run Cell and Add New Cell

```
Alt + Enter
```

### Save Notebook

```
Ctrl + S
```

### Interrupt Kernel

```
Kernel → Interrupt
```

---

## 8. Jupyter Shortcuts

| Shortcut | Action |
|--------|--------|
| Shift + Enter | Run cell |
| Ctrl + Enter | Run cell without moving |
| Alt + Enter | Run cell and add new cell |
| A | Insert cell above |
| B | Insert cell below |
| DD | Delete cell |
| M | Convert to Markdown |
| Y | Convert to Code |

---

## 9. Example Jupyter Notebook Code

### Simple Python Example

```python
print("Welcome to Data Science")
```

### Variables Example

```python
x = 10
y = 20
print(x + y)
```

### Using NumPy

```python
import numpy as np

data = np.array([1,2,3,4,5])
print(data.mean())
```

### Using Pandas

```python
import pandas as pd

data = {
    "Name": ["Alice", "Bob", "Charlie"],
    "Age": [25,30,35]
}

df = pd.DataFrame(data)
print(df)
```

---

## Summary

In this module you learned:

- Data Science career roles
- Technical skills required
- Data Science workflow
- Jupyter Notebook platforms
- Installing Jupyter locally
- Useful commands and shortcuts
- Basic Python examples in notebooks

## Jupyter Notebook Cheat Sheet

For a quick reference guide, see the full cheat sheet:

[Jupyter Notebook Cheat Sheet](jupyter-cheatsheet.md)