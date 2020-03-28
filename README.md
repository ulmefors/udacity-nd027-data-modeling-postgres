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
|-- README.md
|-- create_tables.py
|-- etl.py
|-- sql_queries.py
`-- data
	|-- log_data
	`-- song_data
```

### Run scripts

Drop and recreate tables

```bash
$ python create_tables.py
```

Run ETL pipeline

```bash
$ python etl.py
```