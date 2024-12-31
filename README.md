# Titanic Survivor Prediction with PySpark

This project aims to create a logistic regression model using PySpark to predict the likelihood of survival for passengers on the Titanic, based on a classic dataset about this historical event.

## Dataset

The dataset used in this project is the popular Titanic dataset, which is publicly available in many repositories. It contains information about the passengers, including:

-   **PassengerId:** Unique identifier of the passenger.
-   **Survived:** Indicates whether the passenger survived (1) or not (0).
-   **Pclass:** Passenger class (1 = First, 2 = Second, 3 = Third).
-   **Name:** Name of the passenger.
-   **Sex:** Sex of the passenger.
-   **Age:** Age of the passenger.
-   **SibSp:** Number of siblings/spouses aboard.
-   **Parch:** Number of parents/children aboard.
-   **Ticket:** Passenger's ticket number.
-   **Fare:** Fare paid by the passenger.
-   **Cabin:** Passenger's cabin number.
-   **Embarked:** Port of embarkation (C = Cherbourg, Q = Queenstown, S = Southampton).

## Libraries

The following Python libraries are used:

-   `pyspark`: For data processing with Spark.
-   `pyspark.sql`: For handling dataframes in Spark.
-   `pyspark.ml.feature`: For feature engineering (VectorAssembler, StringIndexer, OneHotEncoder).
-   `pyspark.ml.classification`: For the logistic regression model.
-   `pyspark.ml`: For creating data processing pipelines and models.
-   `pyspark.ml.evaluation`: For evaluating the model's performance (BinaryClassificationEvaluator).

## Process

1.  **Data Loading:** The Titanic dataset is loaded from a CSV file using Spark.
2.  **Data Preprocessing:**
    -   Relevant columns for the model are selected.
    -   Missing values are handled using `na.drop()`.
    -   Categorical variables are converted to numerical variables using `StringIndexer` and `OneHotEncoder` (Sex and Embarked).
3.  **Feature Engineering:**
    -   All predictor variables are combined into a vector using `VectorAssembler`.
4.  **Logistic Regression Model:**
    -   A logistic regression model is created using `LogisticRegression`.
5.  **Pipeline:**
    -   A pipeline is created to automate the data transformation process and model training.
6.  **Model Training and Evaluation:**
    -   The dataset is split into training and test sets.
    -   The model is trained with the training set.
    -   The model is evaluated with the test set using `BinaryClassificationEvaluator`, obtaining the AUC (Area Under the Curve) as a performance metric.
7.  **Results:**
    -   Some predictions of the model are displayed and the AUC is calculated.

## Usage

To run this code, make sure you have the following installed:

-   Python 3.6+
-   Apache Spark
-   PySpark

And that you have the `titanic.csv` file in your working directory.

You can run the code directly in a Spark environment, using a Jupyter notebook or a Python script.

