# Open Modern Analytics Workshop

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/jdkstr/Open-Modern-Analytics-Workshop)

## Introduction
This workshop has its objective to inspire people with the latest open and modern data analytics technologies and how to design the right architectures.

More specifically, a distinction is made between two typical scenarios: batch data and real-time data.

## 1 Batch data processing and analytics with DuckDB

<img src="https://duckdb.org/images/logo-dl/DuckDB_Logo-stacked-dark-mode.svg" width="200" height="100">

### DuckDB Installation
First, we need to install DuckDB to our Codespaces. DuckDB runs almost anywhere and it's very easy to install. Try to find out how to install it. 

<details>

<summary>Hint</summary>

URL

</details>

### Data used in the tasks

- Prishtina Places (restaurant and coffee places) scraped with SerpAPI
- Synthetically generated daily revenue for each place stored in a PostgreSQL database


### 1.1 Tasks using local JSON data


#### 1.1.1 Query JSON and explore the Prishtina Places
<details>

<summary>Hint</summary>

URL

</details>


#### 1.1.2 Clean JSON errors in one of the files
<details>

<summary>Hint</summary>

URL

</details>

#### 1.1.3 Query JSON and find any duplicates
<details>

<summary>Hint</summary>

URL

</details>

#### 1.1.4 Discuss deduplication strategies
<details>

<summary>Hint</summary>

URL

</details>

#### 1.1.5 Query JSON and find the top 10 rated places Prishtina
<details>

<summary>Hint</summary>

URL

</details>

#### 1.1.6 Install and explore the DuckDB geospatial extension by creating geometry point from the latitude and longitude

<details>

<summary>Hint</summary>

[DuckDB Geospatial Extension](https://duckdb.org/docs/stable/core_extensions/spatial/overview)

[DuckDB ST_POINT Function](https://duckdb.org/docs/stable/core_extensions/spatial/overview)

![Coordinate System](https://www.geographyrealm.com/wp-content/uploads/2023/11/map-x-longitude-y-latitude.jpg)

</details>



### 1.2 Tasks using PostgreSQL data

#### 1.2.1 Query the PostgreSQL table with supplied configurations

#### 1.2.2 Query and explore the avg revenue of each restaurant per month

### 1.3 Tasks to create a Ducklake data lakehouse

#### 1.3.1 Create R2 secrets for object storage

#### 1.3.2 Create the ducklake data lakehouse with PostgreSQL as metadata catalog

#### 1.3.3 Create clean table from the JSON files

```sql
CREATE table test as SELECT unnest(local_results, max_depth:=5)
FROM 'datasets/prishtina_places/r*.json';
```

#### 1.3.4 Explore the created Parquet files

#### 1.3.5 Explore the metadata catalog stored in Koyeb PostgreSQL

### 1.4 Final task to further analyze the geospatial data in our data lakehouse

#### 1.4.1 Query the places table and find the 3 closest restaurants to ICK that have a rating over 4.5 and more than 150 reviews

```sql
select title, ST_Point(latitude, longitude) as geoloc, ST_Distance_Sphere(geoloc, 'POINT (42.65507999973656 21.16488168321288)::GEOMETRY') as distance_from_ick from '/datasets/prishtina_places/r*.json' where rating > 4.5 and reviews > 150  order by distance_from_ick asc;
```

## 2 Real-time data processing and analytics with ClickHouse

<img src="https://clickhouse.com/_next/static/media/logo-full.ac8102d5.svg" width="200" height="100">

### ClickHouse Installation
First, we need to install ClickHouse to our Codespaces. ClickHouse also runs almost anywhere and again it's very easy to install. Try to find out how to install it. 

<details>

<summary>Hint</summary>

https://duckdb.org/docs/installation/?version=stable&environment=cli&platform=linux&download_method=direct

</details>