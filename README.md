# Flight Delays Prediction with Spark

## Project Overview

This repository contains the code and resources for a Big Data assignment focused on predicting flight delays using PySpark. The project was developed as part of a course at Universidad Politécnica de Madrid by Cecilia Peccolo, Karla Gonzalez Romero, and Maximilian Boekels.

## Table of Contents

1. [Selected Variables](#selected-variables)
2. [Deleted Variables](#deleted-variables)
3. [Variable Transformations](#variable-transformations)
4. [New Variables](#new-variables)
5. [Machine Learning Algorithm](#machine-learning-algorithm)
6. [Validation and Evaluation](#validation-and-evaluation)
7. [How to Run the Code](#how-to-run-the-code)
   - [Prerequisites](#prerequisites)
   - [Execution Steps](#execution-steps)
   - [Additional Notes](#additional-notes)
8. [Contact Information](#contact-information)

## Selected Variables

The following variables were selected for analysis:

- **Year**: Capture effect of long time trends of flight delays.
- **Month**: Capture effect of the date of the flight on a delay, possibly influenced by weather conditions.
- **DayofMonth**: Capture effect of the specific date of the flight on a delay.
- **DayOfWeek**: Capture effect of the week day of the flight on a delay.
- **UniqueCarrier**: Capture effect of the carrier on flight delays.
- **CRSElapsedTime**: Capture effect of flight duration on delay.
- **ArrDelay**: Target variable.
- **DepDelay**: Capture effect of departure delay on the flight.
- **Origin**: Capture effect of the origin airport.
- **Dest**: Capture effect of the destination airport.
- **TaxiOut**: Capture effect of the time taken to get the plane to the runway.

## Deleted Variables

The following variables were excluded from the analysis:

- **ArrTime**, **ActualElapsedTime**, **AirTime**, **TaxiIn**, **Diverted**, **CarrierDelay**, **WeatherDelay**, **NASDelay**, **SecurityDelay**, **LateAircraftDelay**, **CRSDepTime**, **CRSArrTime**, **FlightNum**, **TailNum**, **Distance**, **CancellationCode**, **Cancelled**, **DepTime**.

## Variable Transformations

All categorical variables and certain integer variables (Year, Month, DayOfWeek, DayofMonth) were encoded using One-Hot Encoding. The remaining integer variables were normalized.

## New Variables

- **DepHours**: Derived from DepTime to handle hour of departure separately.
- **DepMinutes**: Derived from DepTime to handle minute of departure separately.

## Machine Learning Algorithm

Two models were used for prediction:

1. **Decision Tree Regression**: Suitable for non-linear relationships.
2. **Linear Regression**: Suitable for linear relationships.

### Validation and Evaluation

- **Validation**: 5-fold cross-validation with RMSE metric.
- **Evaluation**: The best model was a Linear Regression with One-Hot Encoded non-linear variables, achieving an RMSE of 11.82.

## How to Run the Code

### Prerequisites

- Python installed and configured.
- Create and activate a virtual environment:
  ```bash
  virtualenv venv
  source venv/bin/activate
 ```
- Install required packages:
 ```bash
pip install -r requirements.txt
```

### Execution Steps

1. Ensure `SPARK_HOME` is set to your Spark installation path and `${SPARK_HOME}/bin` is included in your system’s PATH.
2. Activate the virtual environment.
3. Navigate to the application directory.
4. Run the PySpark application:
   ```bash
   spark-submit code.py
   ```
5. (Optional) Monitor execution using Spark UI or cluster manager’s monitoring tools.

### Additional Notes
For cluster deployment, modify the SparkSession/SparkContext configuration in the code to match the cluster setup.

## Contact Information
For any queries, please contact:

Cecilia Peccolo: peccolo.cecilia00@gmail.com
