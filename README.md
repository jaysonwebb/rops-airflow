# rops-airflow

## Project Summary
The purpose of this project is to be able to supplement data in the ROps team Airtable database with data pulled from Presto.  [See this doc](https://docs.google.com/document/d/15Jp_FYyiAMoQO8iGlfNYmN0ZJDALifXhpNdnGTTFJzA/edit?usp=sharing)

## Initial tests
The initial tests were geared toward just being able to read and write from/to an Airtable base (`WriteToAirtable.ipynb`).  The file `secrets.json` has various API KEYS and other secrets necessary to access a given Airtable tab.  The file `secrets2.json` serves the same purpose but has info for the test database that Maggie set up.  The initial tests were completed in early July.  We were able to successfully read, create and update records (we didn't try deleting, but we could, for example to delete duplicates).

You'll want to use 'pip install airtable' to use the airtable api.  Instructions for for [airtable api](https://pypi.org/project/airtable/)

## Second round testing
**Updated 25 July 2022**.  The second round of testing will involve the files `WriteToAirtable_test2.ipynb` and 'secrets2.json' and will be focused on using an account sid from Airtable to (1) query data from Presto (probably for a subset of accounts) and (2) update one or more fields in Airtable.  Again, we're just trying to see if things can be done at all.  We might want to go ahead and scale to using Airflow at this stage.  I'll leave that to Kunal.

### Outcomes from this round of testing 

- July 25: Solved the pagination problem.

## Next
Eventually I think we'll want to: 
- get all this setup in Airflow and running on a schedule
- track errors/data quality
- define/report some kind of metrics on the data itself?  Like percentage of entries with revenue over $X.



