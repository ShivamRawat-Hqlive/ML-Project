# End-to-End Machine Learning Project — Student Performance Prediction

An end-to-end Machine Learning project that predicts **student mathematics performance** based on demographic, educational, and test-related features.

The project follows a modular machine learning workflow covering **data ingestion, exploratory data analysis, preprocessing, model training, evaluation, prediction, and deployment through a Flask web application**.

---

## 📌 Project Overview

The objective of this project is to build a machine learning regression system capable of predicting a student's **Math Score** using features such as:

* Gender
* Race/Ethnicity
* Parental Level of Education
* Lunch Type
* Test Preparation Course
* Reading Score
* Writing Score

Instead of keeping the entire workflow inside a single notebook, the project separates the ML pipeline into reusable components for better organization, maintainability, and deployment.

---

## 🎯 Problem Statement

Student performance can be influenced by several demographic and academic factors.

The goal of this project is to:

1. Analyze the student performance dataset.
2. Identify relationships between student characteristics and academic scores.
3. Prepare the data for machine learning.
4. Train and compare multiple regression algorithms.
5. Select an appropriate model based on evaluation performance.
6. Build a reusable prediction pipeline.
7. Deploy the trained model through a Flask web application.

---

## 🔄 Machine Learning Workflow

```text
Raw Dataset
     │
     ▼
Data Ingestion
     │
     ▼
Train / Test Split
     │
     ▼
Exploratory Data Analysis
     │
     ▼
Data Transformation
     │
     ▼
Feature Engineering
     │
     ▼
Model Training
     │
     ▼
Model Evaluation
     │
     ▼
Best Model Selection
     │
     ▼
Prediction Pipeline
     │
     ▼
Flask Web Application
```

---

## 🧰 Technologies & Tools

### Programming Language

* Python

### Data Analysis

* Pandas
* NumPy
* Matplotlib
* Seaborn

### Machine Learning

* Scikit-learn
* CatBoost
* XGBoost

### Web Application

* Flask
* HTML
* CSS

### Development & Deployment

* Jupyter Notebook
* Git & GitHub
* AWS Elastic Beanstalk configuration

---

## 🤖 Machine Learning Models

The project includes multiple regression algorithms for model comparison, including:

* Linear Regression
* Decision Tree Regressor
* Random Forest Regressor
* Gradient Boosting Regressor
* AdaBoost Regressor
* K-Nearest Neighbors Regressor
* XGBoost Regressor
* CatBoost Regressor

The models are evaluated and compared to identify the best-performing approach for the prediction task.

---

## 📊 Exploratory Data Analysis

The EDA workflow investigates:

* Dataset structure and data types
* Missing values
* Numerical and categorical variables
* Distribution of student scores
* Relationships between reading, writing, and math scores
* Influence of demographic and educational features
* Feature relationships and correlations

The project includes dedicated notebooks for both **EDA and model training**.

---

## 🏗️ Project Architecture

```text
ML-Project/
│
├── .ebextensions/
│   └── Deployment configuration
│
├── artifacts/
│   └── Generated datasets and trained model artifacts
│
├── catboost_info/
│   └── CatBoost training information
│
├── notebook/
│   ├── data/
│   ├── 1. EDA STUDENT PERFORMANCE.ipynb
│   └── 2. MODEL TRAINING.ipynb
│
├── src/
│   ├── components/
│   │   ├── data_ingestion.py
│   │   ├── data_transformation.py
│   │   └── model_trainer.py
│   │
│   ├── pipeline/
│   │   ├── predict_pipeline.py
│   │   └── train_pipeline.py
│   │
│   ├── exception.py
│   ├── logger.py
│   └── utils.py
│
├── templates/
│   ├── home.html
│   └── index.html
│
├── application.py
├── requirements.txt
├── setup.py
└── README.md
```

---

## 🔍 Key Components

### 1. Data Ingestion

The data ingestion component is responsible for:

* Reading the raw dataset
* Splitting the dataset into training and testing sets
* Saving processed datasets into the artifacts directory

This creates a reproducible starting point for the rest of the ML pipeline.

---

### 2. Data Transformation

The transformation pipeline prepares the dataset for machine learning.

It handles:

* Numerical feature processing
* Categorical feature encoding
* Missing-value handling
* Feature scaling where required
* Construction of the preprocessing pipeline

The transformation object is saved so that the same preprocessing logic can be reused during prediction.

---

### 3. Model Training

The model training component trains and evaluates multiple regression algorithms.

The purpose is not simply to train one model, but to compare different approaches and identify a suitable model for the dataset.

---

### 4. Model Evaluation

Models are evaluated using regression performance metrics such as:

* **R² Score**

Model comparison helps determine which algorithm performs best on the test data.

---

### 5. Prediction Pipeline

The prediction pipeline provides a reusable interface for making predictions on new student data.

The pipeline:

```text
Input Data
    ↓
Feature Conversion
    ↓
Saved Preprocessor
    ↓
Trained Model
    ↓
Predicted Math Score
```

This separates prediction logic from the Flask application.

---

## 🌐 Flask Web Application

The trained machine learning pipeline is integrated into a Flask web application.

Users can enter student information through the web interface, and the application passes the input through the prediction pipeline to generate the predicted mathematics score.

The Flask application contains routes for:

* Home page
* Prediction form
* Model prediction

The application uses the reusable `PredictPipeline` rather than duplicating preprocessing and model logic inside the web application.

---

## 🚀 How to Run the Project Locally

### 1. Clone the repository

```bash
git clone https://github.com/ShivamRawat-Hqlive/ML-Project.git
```

### 2. Navigate to the project

```bash
cd ML-Project
```

### 3. Create a virtual environment

Using Conda:

```bash
conda create -n mlproject python=3.10 -y
```

Activate it:

```bash
conda activate mlproject
```

Or using Python's built-in virtual environment:

```bash
python -m venv venv
```

Activate on Windows:

```bash
venv\Scripts\activate
```

---

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

---

### 5. Run the Flask application

```bash
python application.py
```

The application will start locally.

Open the displayed local Flask address in your browser.

---

## 📓 Running the Notebooks

The repository contains separate notebooks for exploration and model development.

### EDA

```text
notebook/
└── 1. EDA STUDENT PERFORMANCE.ipynb
```

This notebook contains the exploratory analysis of the student performance dataset.

### Model Training

```text
notebook/
└── 2. MODEL TRAINING.ipynb
```

This notebook contains model training and evaluation experiments.

The production-oriented implementation is then organized into the `src` package.

---

## 🧩 Why This Project Is Structured This Way

A major objective of this project is to move beyond a simple Jupyter Notebook implementation.

Instead of:

```text
Notebook → Model → Prediction
```

the project follows a more maintainable structure:

```text
Data
 ↓
Ingestion
 ↓
Transformation
 ↓
Training
 ↓
Evaluation
 ↓
Saved Model
 ↓
Prediction Pipeline
 ↓
Flask Application
```

This makes individual components easier to maintain, test, and reuse.

---

## 📁 Artifacts

The `artifacts` directory contains generated outputs from different stages of the machine learning workflow, such as:

* Training dataset
* Testing dataset
* Transformed data
* Trained model
* Preprocessing objects

These artifacts allow the prediction pipeline to reuse previously generated preprocessing and model objects.

---

## ☁️ Deployment

The project includes AWS Elastic Beanstalk configuration through the `.ebextensions` directory.

The Flask application is therefore structured with deployment in mind rather than being limited to local notebook execution.

---

## 💡 Key Learning Outcomes

Through this project, I worked with:

* End-to-end machine learning workflows
* Regression problems
* Exploratory Data Analysis
* Feature engineering
* Data preprocessing
* Categorical feature encoding
* Model comparison
* Model evaluation
* Modular Python project architecture
* Custom exception handling
* Logging
* Training and prediction pipelines
* Flask model deployment
* Git and GitHub
* Cloud deployment configuration

---

## 📌 Project Highlights

**Problem:** Predict student mathematics performance

**Type:** Supervised Machine Learning — Regression

**Input:** Demographic, educational, and academic features

**Output:** Predicted Mathematics Score

**Primary Language:** Python

**Deployment:** Flask Web Application

**Architecture:** Modular End-to-End ML Pipeline

---

## 👨‍💻 Author

**Shivam Rawat**

Data Analyst | Machine Learning Enthusiast

GitHub: [ShivamRawat-Hqlive](https://github.com/ShivamRawat-Hqlive)

---

## ⭐ Future Improvements

Potential improvements for the project include:

* Add automated unit and integration tests
* Add CI/CD using GitHub Actions
* Add model versioning
* Add experiment tracking with MLflow
* Add automated model monitoring
* Improve API validation and error handling
* Containerize the application using Docker
* Add a production WSGI server
* Add automated data validation
* Add model performance monitoring after deployment

---

## 📄 License

This project is intended for educational and portfolio purposes.
