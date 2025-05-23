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
   `docker compose --profile flower up -d `

After the compose builds the project, the tutorial's services will be available at:

|        Service        |          URL           |
| :-------------------: | :--------------------: |
| Airflow Web Interface | http://localhost:8080  |
|        MlFlow         | http://localhost:5000  |
|        Flower         | http://localhost:5555  |
|     Spark Master      | http://localhost:8090  |
|     Mongo Express     | http://localhost:28081 |

### Setting Up

1. Navigate to Airflow's web interface
2. Log in with `username: airflow` and `password: airflow`
3. Navigate into the connections section in admin dropdown.
4. Click the <b>add new record</b> option
5. Set `Connection Id` to <b>mongo_default</b>
6. Select <b>MongoDB</b> in `Connection type` dropdown menu
7. Provide `Host`, `Username`, `Password` and `Port` in accordance with the [.env](.env) file.
8. Save connection

An example connection configuration is depicted below:
![Airflow connection configuration](/documentation/screenshots/airflow-connection-settings.png?raw=true "Airflow Connection Configuration")

### Technologies used

- [Docker][Docker-url]
- [Docker-compose][Docker-compose-url]
- [Airflow][Airflow-url]
- [Apache Spark][Apache-Spark-url]
- [Flower][Flower-url]
- [MongoDB][Mongo-url]
- [Mongo Express UI][Mongo-express-repo]

[Airflow-url]: https://airflow.apache.org/
[Docker-url]: https://docs.docker.com/
[Docker-compose-url]: https://docs.docker.com/compose/
[Flower-url]: https://flower.readthedocs.io/en/latest/
[Apache-Spark-url]: https://spark.apache.org/
[Mongo-url]: https://www.mongodb.com/
[Mongo-express-repo]: https://github.com/mongo-express/mongo-express?tab=MIT-1-ov-file
