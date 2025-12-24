# IT4142E_Real_Estate_Analysis

This repository contains code for real estate data analysis, including data crawling, preprocessing, modeling, and a simple web application for prediction.

## Table of Contents

- [IT4142E\_Real\_Estate\_Analysis](#it4142e_real_estate_analysis)
  - [Table of Contents](#table-of-contents)
  - [Quick Demo](#quick-demo)
  - [Data Crawling](#data-crawling)
    - [Mogi.vn Data](#mogivn-data)
    - [Nhatot.com Data](#nhatotcom-data)
  - [Running the Application](#running-the-application)
  - [Changing the Prediction Model](#changing-the-prediction-model)
  - [Task Distribution](#task-distribution)

## Quick Demo

For a quick demonstration of the application, visit: [https://housing12.streamlit.app/](https://housing12.streamlit.app/)

## Data Crawling

To collect real estate data, navigate to the respective crawler directories and run the `runner.py` script.

### Mogi.vn Data

1.  Navigate to the Mogi crawler directory:
    ```bash
    cd crawler/mogi_crawler
    ```
2.  Run the crawler:
    ```bash
    python runner.py
    ```

### Nhatot.com Data

1.  Navigate to the Nhatot crawler directory:
    ```bash
    cd crawler/nhatot_crawler
    ```
2.  Run the crawler:
    ```bash
    python runner.py
    ```

## Running the Application

This application is built using Streamlit.

1.  Install the required Python packages. It's recommended to create a virtual environment first:
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    pip install -r requirements.txt
    ```
2.  From the root directory of the project, run the main dashboard file:
    ```bash
    streamlit run Dashboard.py
    ```
3.  The application will open in your web browser.

## Changing the Prediction Model

The prediction page (`pages/2_Prediction.py`) uses a pre-trained model. To switch the model used for predictions:

1.  Open the file `pages/2_Prediction.py`.
2.  Locate the `model_path` variable within the `predict` function.
3.  Update the `model_path` to point to the desired model file in the `saved_models` directory.

    For example, to switch from the Random Forest model (`random_forest_model.pkl`) to the XGBoost model (`xgb.pkl`):

    ```python
    # Original (example for Random Forest)
    model_path = 'saved_models/random_forest_model.pkl'

    # To change to XGBoost model
    # model_path = 'saved_models/xgb.pkl' # Uncomment and update this line
    ```
    Note: If switching to `xgb.pkl`, ensure the `xgboost` library is installed (it's included in `requirements.txt`).

## Task Distribution

| Name | Tasks |
| :--- | :---- |
| Vu Binh Minh | Crawl data from mogi.vn, Preprocess data, Train RandomForest |
| Bui Dang Quy | Crawl data from onehousing.vn, EDA, Train XGBoost |
| Ngo Minh Trung | Crawl data from nhatot.com, Standardize and split the data, Build web, Train Ridge Regression |
