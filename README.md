# Open Modern Analytics Workshop

## Introduction
This workshop has its objective to inspire people with the latest open and modern data analytics technologies and how to design the right architectures.

More specifically, a distinction is made between two typical scenarios: batch data and real-time data.

## 1 Batch data processing and analytics with DuckDB

![DuckDB](https://duckdb.org/images/logo-dl/DuckDB_Logo-horizontal.svg)

### Data

- Prishtina Places (restaurant and coffee places) scraped with SerpAPI
- Synthetically generated daily revenue for each place stored in a PostgreSQL database

### 1.1 Tasks using local JSON data

- Query JSON and explore the Prishtina Places
- Clean JSON errors in one of the files
- Query JSON and find any duplicates
- Discuss deduplication strategies
- Query JSON and find the top 10 rated places Prishtina
- Install and explore the DuckDB geospatial extension
<details>

<summary>Hint</summary>

![Coordinate System](https://www.geographyrealm.com/wp-content/uploads/2023/11/map-x-longitude-y-latitude.jpg)

</details>



### 1.2 Tasks using PostgreSQL data

- Query the PostgreSQL table with supplied configurations
- Query and explore the avg revenue of each restaurant per month

### 1.3 Tasks to create Ducklake data lakehouse

- Create R2 secrets for object storage
- Create the ducklake data lakehouse with PostgreSQL as metadata catalog
- Create clean table from the JSON files
- Explore the created Parquet files
- Explore the metadata catalog stored in Koyeb PostgreSQL

### 1.4 Final task to further analyze the geospatial data in our data lakehouse
- Query the places table and find the 3 closest restaurants to ICK that have a rating over 4.5 and more than 150 reviews

## 2 Real-time data processing and analytics with ClickHouse

![ClickHouse](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRGASq3Is0TjN_RK-3ZaEjrtgyTqnOM-klPVQ&s)