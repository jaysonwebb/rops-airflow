# rops-airflow

## Project Summary
The purpose of this project is to be able to supplement data in the ROps team Airtable database with data pulled from Presto.  [See this doc](https://docs.google.com/document/d/15Jp_FYyiAMoQO8iGlfNYmN0ZJDALifXhpNdnGTTFJzA/edit?usp=sharing)

## Initial tests
The initial tests were geared toward just being able to read and write from/to an Airtable base (`WriteToAirtable.ipynb`).  The file `secrets.json` has various API KEYS and other secrets necessary to access a given Airtable tab.  The file `secrets2.json` serves the same purpose but has info for the test database that Maggie set up.  The initial tests were completed in early July.  We were able to successfully read, create and update records (we didn't try deleting, but we could, for example to delete duplicates).

You'll want to use 'pip install airtable' to use the airtable api.  Instructions for for [airtable api](https://pypi.org/project/airtable/), which also describes other dependencies you'll want to install.

## Second round testing
**Updated 26 July 2022**.  The second round of testing is underway and involves the files `WriteToAirtable_test2.ipynb` and 'secrets2.json'.  It is focused on reading multiple pages from the Airtable base.  Right now there are 126 pages containing 12,546 records.  Airtable limits pages to 100 records.  This is test data, so it won't grow, but it does have the structure of the "real" data.  

I think we have successfully figured out how to deal with pagination.  I don't love the data structure it's returning right now, a list that contains two lists: List 1 has 126 dict structures, one for each page of data.  List 2 has a count of items on each page.  Summing across this list gives the total page count.  There is probably a better way to do this.  We might consider dropping the count altogether.  It's really there for debugging purposes at this point.

**The next step** will be using an account sid from the Airtable data to (1) query data from Presto (probably for a subset of accounts) and (2) update one or more fields in Airtable.  Again, we're just trying to see if things can be done at all. 

### Outcomes from this round of testing 

- July 25: Solved the pagination problem.
- July 26: How do we map email address to a company.  We don't have account sid

## Next
Eventually I think we'll want to: 
- get all this setup in Airflow and running on a schedule
- track errors/data quality
- define/report some kind of metrics on the data itself?  Like percentage of entries with revenue over $X.



