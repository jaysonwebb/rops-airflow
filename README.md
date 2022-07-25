# rops-airflow

## Project Summary
The purpose of this project is to be able to supplement data in the ROps team Airtable database with data pulled from Presto.  [See this doc](https://docs.google.com/document/d/15Jp_FYyiAMoQO8iGlfNYmN0ZJDALifXhpNdnGTTFJzA/edit?usp=sharing)

## Initial tests
The initial tests are geared toward just being able to read and write to/from an Airtable base (`WriteToAirtable.ipynb`).  The file `secrets.json` has various API KEYS and other secrets necessary to access a given Airtable tab.  The file `secrets2.json` serves the same purpose but has info for the test database that Maggie set up.

