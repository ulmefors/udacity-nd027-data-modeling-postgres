# udacity-nd027-data-modeling-postgres

Project submission for Udacity Data Engineering Nanodegree - Data Modeling with Postgres

## Summary

This project combines song listen log files with song metadata to facilitate analytics on denormalized table.

## Install

Unzip data and prepare Python 3 environment

```bash
$ unzip data.zip
$ pip install -r requirements.txt
```

Data files should be in data directory in root directory alongside python scripts

```
.
|-- create_tables.py
|-- etl.ipynb
|-- etl.py
|-- sql_queries.py
|-- test.ipynb
`-- data
    |-- log_data
    `-- song_data
```

## Files

### `create_tables.py`

* Drop and recreate database ` sparkifydb`
* Drop and recreate tables defined in `sql_queries.py`

### `sql_queries.py`

* Define create and insert statements for tables `songplays`, `users`, `songs`, `artists`, and `time`
* Define select statements to identify songs

### `etl.py`

1. Load data from logs and metadata
2. Filter relevant rows and columns
3. Extract time components and join datasets to create required fields
4. Insert into correct tables

### `test.ipynb`

* Interactive environment to verify that data has been inserted in expected format in each table

### `test.ipynb`

* Interactive environment to verify that data has been inserted in expected format in each table

### `etl.ipynb`

* Interactive environment to validate data conversion and table inserts

## Run scripts

Drop and recreate tables

```bash
$ python create_tables.py
```

Run ETL pipeline

```bash
$ python etl.py
```

Example analysis script (count streams per subscription type)

```bash
$ ipython
> %load_ext sql
> %sql postgresql://student:student@127.0.0.1/sparkifydb
> %sql SELECT level, count(level) FROM songplays GROUP BY level

[('free', 1229), ('paid', 5591)]
```

## Further work

* Insert data using the COPY command to bulk insert log files instead of using INSERT on one row at a time
* Add data quality checks
* Create a dashboard for analytic queries on new database