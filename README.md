# MLOps Pipeline using Apache Airflow

## Project Overview
This project demonstrates building an MLOps pipeline using Apache Airflow to automate tasks such as data preprocessing, model training, and deployment. The pipeline is designed to streamline the analysis of screentime data and predict app usage efficiently.

## Dataset
The dataset contains the following columns:
- `Date`: Usage day
- `App`: The application (e.g., Instagram, WhatsApp)
- `Usage`: Minutes spent
- `Notifications`: Alerts received
- `Times Opened`: Number of times the app was launched

Download the dataset [here](#).

## Features of the Pipeline
1. **Automated Data Preprocessing**:
   - Handles missing values and duplicates.
   - Extracts temporal features (`DayOfWeek`, `Month`).
   - Encodes categorical data using one-hot encoding.
   - Scales numerical features using `MinMaxScaler`.
   - Performs feature engineering for additional predictive power.

2. **Model Training**:
   - Trains a Random Forest Regressor to predict app usage.
   - Evaluates performance using Mean Absolute Error (MAE).

3. **Pipeline Automation**:
   - Uses Apache Airflow to automate data preprocessing tasks daily via a Directed Acyclic Graph (DAG).

## Technologies Used
- **Python**: Data preprocessing, feature engineering, and model training.
- **Apache Airflow**: Task automation and pipeline orchestration.
- **scikit-learn**: Machine learning model training and evaluation.
- **pandas**: Data manipulation and analysis.

## Installation and Setup
### Prerequisites
- Python 3.7+
- Apache Airflow
- Required Python libraries:


## Install Dependencies
To install the required dependencies, run the following command:

```bash
pip install pandas scikit-learn apache-airflow



Initialize the Airflow metadata database:

airflow db init


Start the Airflow webserver:
airflow webserver --port 8080

Start the Airflow scheduler:
airflow scheduler


Access the Airflow UI at http://localhost:8080 and enable the data_preprocessing DAG.

Usage
Place the dataset file (screentime_analysis.csv) in the project directory.

Trigger the data_preprocessing DAG from the Airflow UI.

The preprocessed data will be saved as preprocessed_screentime_analysis.csv.

Run the model training script:
python train_model.py


Review the model performance metrics in the output.

Project Files
preprocess_data.py: Contains the data preprocessing logic.
train_model.py: Script for model training and evaluation.
airflow_dag.py: DAG definition for Apache Airflow.
README.md: Project documentation.


Model Performance
The pipeline achieves a Mean Absolute Error (MAE) of approximately 15.4 minutes for screentime prediction.

Future Enhancements
Optimize the model for better accuracy.
Implement monitoring and logging for pipeline tasks.
Extend the pipeline to support real-time streaming data.
