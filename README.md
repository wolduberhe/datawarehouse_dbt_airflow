
# Data Engineering: Data warehouse tech stack with Postgres, DBT, and Airflow

You and your colleagues have joined to create an AI startup that deploys sensors to businesses, collects data from all activities in a business - people’s interaction, traffic flows, smart appliances installed in a company. Your startup helps organizations obtain critical intelligence based on public and private data they collect and organize. 

A city traffic department wants to collect traffic data using swarm UAVs (drones) from a number of locations in the city and use the data collected for improving traffic flow in the city and for a number of other undisclosed projects. Your startup is responsible for creating a scalable data warehouse that will host the vehicle trajectory data extracted by analysing footage taken by swarm drones and static roadside cameras.

The data warehouse should take into account future needs, organise data such that a number of downstream projects query the data efficiently. You should use the Extract Load Transform (ELT) framework using DBT.  Unlike the Extract, Transform, Load (ETL), the ELT framework helps analytic engineers in the city traffic department setup transformation workflows on a need basis.  

___

This project tried to implement the following core tasks
- A “data warehouse” (PostgresQL)
- An orchestration service (Airflow)
- An ELT tool (dbt)
___

# Deployment
## Redash Setup

First cd to redash directory 
```
cd redash
```
## Create an environment file here
`.env` Shoud contain the following
```bash
REDASH_HOST=http://localhost/redash
PYTHONUNBUFFERED=0
REDASH_LOG_LEVEL=INFO
REDASH_REDIS_URL=redis://redis:6379/0
POSTGRES_PASSWORD=password
REDASH_COOKIE_SECRET=redash-selfhosted
REDASH_SECRET_KEY=redash-selfhosted
REDASH_DATABASE_URL={postgresql+psycopg2://username:password@host/dbname}
```
Then run 

```bash
docker-compose run --rm server create_db 
docker-compose up -d

# your redash dashboard should be running on port 5000
```

Please, find the deployed dbt warehouse documentation from [here](https://data-engineering-dwh.netlify.app/#!/overview)


# Screenshots
### Airflow & DBT
Two Dags
![App Screenshot](./screenshots/DAGs.jpg)

Acyclic Graph representation
![App Screenshot](./screenshots/Directed%20Asyclic%20Graph.jpg)

Dbt tasks with graph
![App Screenshot](./screenshots/dbt-dags.jpg)

DBT docs
![App Screenshot](./screenshots/docs.jpg)

## redash Dashboard
![App Screenshot](./screenshots/redash-board%20I.jpg)

![App Screenshot](./screenshots/redash-board%20II.jpg)

<br>

# Tech Stacks
|       |  | | | | | | |
| ----------- | ----------- | -------- | ---------| -----------| -------| -----------| -------|
| <img height="80" src="https://user-images.githubusercontent.com/25181517/117208740-bfb78400-adf5-11eb-97bb-09072b6bedfc.png">   |*postgreSQLs*| | <img height="80" src="https://www.docker.com/wp-content/uploads/2022/03/vertical-logo-monochromatic.png">   |*docker*| | <img height="80" src="https://avatars.githubusercontent.com/u/10746780?s=280&v=4">   |*redash*|
| <img height="80" src="https://static-00.iconduck.com/assets.00/airflow-icon-512x512-tpr318yf.png">   |*airflow*| | <img height="80" src="https://seeklogo.com/images/D/dbt-logo-500AB0BAA7-seeklogo.com.png">   |*dbt*|

<br>
<br>

# Authors

- [@Nathnael12](https://www.github.com/nathnael12)


## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.


## Feedback

If you have any feedback, please reach out to me at natnaelmasresha@gmail.com


