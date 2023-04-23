# Week-8-Data-Pipelines-with-Airflow-Independent-Assignment

## Project Title
### Data Pipeline using Airflow on Google Cloud Platform

## Project Description
The goal of this project is to build a data pipeline using Airflow to extract, transform, and load data from three CSV files into a PostgreSQL database. The pipeline will be built using Airflow on Google Cloud Platform.

## Prerequisites
* Google Cloud Platform account
* Basic knowledge of Google Cloud Platform
* Basic knowledge of Airflow
* Python 3.x installed on local machine

## Setup
* Create a new project on Google Cloud Platform.
* Enable the following APIs:
* Compute Engine API *
* Cloud SQL Admin API *
* Cloud SQL API *
* Cloud Build API *
* Create a service account and download the service account key in JSON format. This key will be used for authentication.
* Create a PostgreSQL instance on Google Cloud SQL.
* Create a new database in the PostgreSQL instance.
* Create a Compute Engine instance on Google Cloud Platform.
* SSH into the Compute Engine instance.
* Install Airflow using the following command:

> export AIRFLOW_HOME=~/airflow <br>
> echo AIRFLOW_HOME <br> 
> sudo apt-get update <br>
> sudo apt-get install -y python3-pip <br>
> sudo apt-get install -y python3-venv <br>
> python3 -m venv ~/airflow/venv <br>
> source ~/airflow/venv/bin/activate <br>
> pip install apache-airflow <br>

* Configure the Airflow database using the following commands:<br>

airflow db init
airflow users create \
    --username admin \
    --password admin \
    --firstname Emmanuel \
    --lastname Odenyire \
    --role Admin \
    --email eodenyire@gmail.com


* Create the following folders in the $AIRFLOW_HOME directory:
   mkdir dags<br>
   mkdir plugins <br>
* Copy the Python files in the dags and plugins folders of this project to the respective folders in $AIRFLOW_HOME.
* Install the following Python packages:

   pip install pandas<br>
   pip install psycopg2-binary<br>
* Edit the config.py file in the plugins folder and update the PostgreSQL database credentials.
* Start the Airflow webserver and scheduler using the following commands:

   airflow webserver -p 8080 <br>
   airflow scheduler <br>
* Open a web browser and navigate to http://<COMPUTE_ENGINE_EXTERNAL_IP>:8080.
* Turn on the data_pipeline DAG.
* Check the status of the DAG and verify that it has completed successfully.
* Check the PostgreSQL database to verify that the data has been loaded.

## Running the ETL Process
1. The extract_data() function in the extract_data.py <br>
Python file extracts the data from the three CSV files and stores it in Pandas dataframes.<br>

2. The transform_data() function in the transform_data.py Python file transforms the data by merging the dataframes and calculating the customer lifetime value.<br>
3. The load_data() function in the load_data.py Python file loads the transformed data into the PostgreSQL database.<br>

## Authors
Emmanuel Odenyire Anyira

Google colab notebook:  https://colab.research.google.com/drive/12pE7ax3L5YRTSAfBEKw1lxl2JwozUjaA?usp=sharing

This assisgnment has two deliverables.<br>
I was expected to deliver a GitHub repository with the following:<br>
● Airflow DAG file for the data pipeline.<br>
● Documentation of the pipeline.<br>
○ Highlight at least 3 best practices used during the implementation.<br>
○ Recommendations for deployment and running the pipeline in a cloud-based
provider.

These deliverables can be found in the assignmentfiles folder in this repository, although the colab link in this ReadMe file also have a well explained and documented DAG with all the required explainations and docuemntation on this project. Mark the files in the assignmentfiles folder.<br>







