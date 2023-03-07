# Finance-Complaint 


### Problem Statement
Complaints can provide valuable insights into the issues that people are facing in the marketplace, allowing us to better understand the underlying reasons behind these problems. By analyzing these complaints, we can identify areas where modifications to existing financial products may be needed to address these issues and improve overall customer satisfaction.



### Solution Proposed 
We can leverage machine learning to address complaints about financial products by analyzing existing complaints to identify problematic issues. This analysis can help us create a model that can quickly identify newly registered complaints and determine whether they are likely to be disputed by the customer or not. By taking quick action to resolve these issues, companies can better satisfy their customers' needs and improve overall customer satisfaction.


## Tech Stack Used
1. Python 
2. PySpark
3. PySpark ML
4. Airflow as Scheduler
5. MongoDB


## Infrastructure Required.

1. GCP Compute Engine
2. S3 Bucket
3. Artifact Registry

## Dashboarding
1. Grafana
2. Prometheus
3. Node Exporter
4. Promtail
5. Loki

## How to run?

## WorkFLow setup

Create .env file

```
AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
MONGO_DB_URL=
TRAINING=1
PREDICTION=1
```
1- Trigger
0- Bypass

Build docker image
```
docker build -t tc:lts .
```

Lauch docker image

```
docker run -it -v $(pwd)/finance_artifact:/app/finance_artifact  --env-file=$(pwd)/.env fc:lts
```

Steps to run project in local system


1. Build docker image
   ```
   docker build -t fc:lts .
   ```
2. Set envment variable
```
export AWS_ACCESS_KEY_ID=
export AWS_SECRET_ACCESS_KEY=
export MONGO_DB_URL=
export AWS_DEFAULT_REGION="us-east"
export IMAGE_NAME=fc:lts
```
3. To start your application
```
docker-compose up
```
4. To stop your application
```
docker-compose down
``` 



In your local system to setup airflow 


AIRFLOW SETUP

## How to setup airflow

Set airflow directory
```
export AIRFLOW_HOME="[Your airflow directroy]"
```

To install airflow 
```
pip install apache-airflow
```

To configure databse
```
airflow db init
```

To create login user for airflow
```
airflow users create  -e [email] -f [firstname] -l [lastname] -p [password] -r [role]  -u [username]
```
To start scheduler
```
airflow scheduler
```
To launch airflow server
```
airflow webserver -p <port_number>
```

Update in airflow.cfg
```
enable_xcom_pickling = True
```
