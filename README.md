# Airflow Tutorial

My version of the Airflow tutorial (https://airflow.incubator.apache.org/tutorial.html#)

## To set up the repo
```sh
git clone git@github.com:parsing-science/airflow_tutorial.git
cd airflow_tutorial
virtualenv venv
source venv/bin/activate
pip install -r requirements.txt
```
## Script validation
```sh
cd airflow_tutorial
source venv/bin/activate
python ~/airflow/dags/tutorial.py
airflow list_dags
airflow list_tasks tutorial
airflow list_tasks tutorial --tree
```

## Testing the code
```sh
airflow updatedb #This step is not listed in the tutorial, but you need to do it first.
airflow test tutorial print_date 2015-06-01
airflow test tutorial sleep 2015-06-01
airflow test tutorial templated 2015-06-01
```

## Backfill
```sh
airflow webserver
airflow backfill tutorial -s 2015-06-01 -e 2015-06-07 #In a new terminal window
```




