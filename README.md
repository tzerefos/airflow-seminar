# Airflow Seminar

## Deployment

### Requirements

In order to deploy this tutorial the following hardware and software requirements must be met.

#### Hardware

- Memory: 16 GB RAM
- Processor: Intel(R) Core(TM) i5-6500 or greater / AMD Ryzen 5 3600 or greater
- Storage: 15 GB available space

#### Software

- [Docker][Docker-url] version >= 27.4.0
- [Docker-compose][Docker-compose-url] version >= 2.29.2

### Installation

To install the project, run the following steps:

1. Run database migrations and create the first user account  
   `docker compose up airflow-init`

1. Initiate Airflow with:  
   `docker compose up -d`

After the compose builds the project, the tutorial's services will be available at:

|        Service        |          URL          |
| :-------------------: | :-------------------: |
| Airflow Web Interface | http://localhost:8080 |

## Tutorial

### Simple Tutorial
```python
def hello_world():
    print("Hello, Airflow!")

dag = DAG('hello_world_dag', start_date=datetime(2025, 1, 1), schedule_interval='@daily')

task = PythonOperator(
    task_id='say_hello',
    python_callable=hello_world,
    dag=dag,
)
```

### Large Scale Data Tutorial

### Technologies used

- [Docker][Docker-url]
- [Docker-compose][Docker-compose-url]
- [Airflow][Airflow-url]
- [Sensors][Sensors-Url]
- [Python Sensors][Python-Sensors-Url]

[Airflow-url]: https://airflow.apache.org/
[Docker-url]: https://docs.docker.com/
[Docker-compose-url]: https://docs.docker.com/compose/
[Sensors-url]: https://airflow.apache.org/docs/apache-airflow/stable/core-concepts/sensors.html
[Python-Sensors-Url]: https://airflow.apache.org/docs/apache-airflow/stable/howto/operator/python.html#pythonsensor
[airflow-sensors-url]: https://airflow.apache.org/docs/apache-airflow/stable/core-concepts/sensors.html
