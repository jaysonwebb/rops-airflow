# rops-airflow

## Project Summary
The purpose of this project is to be able to supplement data in the ROps team Airtable database with data pulled from Presto.  [See this doc](https://docs.google.com/document/d/15Jp_FYyiAMoQO8iGlfNYmN0ZJDALifXhpNdnGTTFJzA/edit?usp=sharing)

## Initial tests
The initial tests were geared toward just being able to read and write to/from an Airtable base (`WriteToAirtable.ipynb`).  The file `secrets.json` has various API KEYS and other secrets necessary to access a given Airtable tab.  The file `secrets2.json` serves the same purpose but has info for the test database that Maggie set up.  The initial tests were completed in early July.

## Second round testing
Updated 25 July 2022.  The second round of testing will involve the files `WriteToAirtable.ipynb` and 'secrets2.json' and will be focused on using an account sid from Airtable to (1) query data from Presto and (2) update one or more fields in Airtable.  Again, we're just trying to see if things can be done at all.  We might want to go ahead and scale to using Airflow at this stage.  I'll leave that to Kunal.

### Questions from this round of testing

- One

