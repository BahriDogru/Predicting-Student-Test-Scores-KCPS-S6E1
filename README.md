# Synthetic vs Original Data: Model Performance Analysis (Kaggle Playground Series - S6E1)

## Project Overview

This project was developed for participation in the [Kaggle Playground Series - Season 6, Episode 1](https://www.kaggle.com/competitions/playground-series-s6e1) machine learning competition. The main objective of the competition is to accurately predict the grades that students with varying performance levels will receive on an exam.


### Dataset

The dataset consists of student-related attributes used to predict exam performance.
Key feature groups include:

Study-related features:
Study hours, class attendance rate, preparation level

Lifestyle features:
Sleep duration and daily habits

Target variable:
Exam score (regression task)

The same feature set is used across all datasets to ensure a fair comparison.


## Workflow

The project involves the following steps:

**1 - Exploratory Data Analysis (EDA)**

Understanding feature distributions and basic relationships

**2 - Data Preprocessing**
- Handling missing values
- Outlier detection and analysis
- Feature engineering
- Categorical encoding
- Feature scaling

**3 - Model Comparison**
- Decision Tree
- Random Forest
- LightGBM
- XGBoost
    
*Models are evaluated on all three datasets using cross-validated RMSE.*

**4 - Hyperparameter Tuning**
- Performed only on the synthetic dataset
- LightGBM and XGBoost optimized separately

**5 - Final Training & Prediction**
- Best-performing models are trained
- Predictions generated for submission

**6 - Experiment Tracking**
- MLflow is used to log parameters and evaluation metrics


## Setup and Running

To run this project on your local machine, follow these steps:

1.  **Clone the Repository**:
    ```bash
    git clone https://github.com/BahriDogru/Predict_Student_Test_Score.git

    cd Predicting-Student-Test-Scores-KCPS-S6E1
    ```
2.  **Install Required Libraries (using Conda environment):**:
    ```bash
    conda env create -f environment.yml
    conda activate stdt_score_pred_env
    ```
    This will install all required dependencies listed in the environment.yml file.


3.  **Download the Dataset**:
    Download the `train.csv` and `test.csv` files from the [Kaggle competition page](https://www.kaggle.com/competitions/playground-series-s6e1). Place these files inside a folder named `data/` in your project's root directory.
    ```
    .
    ├── main.ipynb
    ├── mlruns
    ├── data/
    │   ├── train.csv
    │   ├── test.csv
    │   ├── Exam_Score_Prediction.csv
    │   └── sample_submission.csv
    ├── README.md
    └── mlflow.db
    ```
4.  **Run the Code**:
    ```bash
    python main.ipynb
    ```
    This command will train the model, make predictions, and generate the `submission.csv` file.

## Results

Key observations from the experiments:

- Models trained on synthetic data consistently outperform those trained on original data

- Original data introduces more noise and results in higher RMSE

- Combining synthetic and original data does not necessarily improve performance

- Naively merging datasets with different distributions may degrade model performance

These findings highlight the importance of understanding data generation processes in synthetic datasets, especially in competition settings.
